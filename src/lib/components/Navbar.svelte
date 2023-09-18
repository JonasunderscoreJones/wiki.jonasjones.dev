<script>
	// @ts-nocheck

	let data = import.meta.glob("/src/routes/**/+page.md");
	let paths = data;
	export let items;

	/**
	 * @param {Record<string, () => Promise<unknown>>} paths
	 */
	function buildHierarchy(paths) {
		const nestedList = {};
		let fixedpaths = [];
		/**
		 * @type {string[]}
		 */
		let fixedpaths2 = [];
		fixedpaths = Object.keys(paths);
		fixedpaths.forEach((path) => {
			const fixedpath = path
				.replace("/+page.md", "")
				.replace("/src/routes", "");
			fixedpaths2.push(fixedpath);
		});
		fixedpaths2.forEach((folder) => {
			const parts = folder.split("/").filter(Boolean);
			let currentNode = nestedList;

			parts.forEach((part) => {
				if (!currentNode[part]) {
					currentNode[part] = {};
				}
				currentNode = currentNode[part];
			});
		});

		return nestedList;
	}

	const nestedFolders = buildHierarchy(paths);
	console.log(nestedFolders)

	// Helper function to recursively render the nested list
	/**
	 * @param {{ [x: string]: any; }} node
	 */
	// function renderNestedList(node, prefix = "") {
	// 	return Object.keys(node)
	// 		.map((key) => {
	// 			const fullPath = `${prefix}/${key}`;
	// 			return `<li><a href="${fullPath}">${key}</a><ul>${renderNestedList(
	// 				node[key],
	// 				fullPath
	// 			)}</ul></li>`;
	// 		})
	// 		.join("");
	// }

	function createHtmlList(obj, parentPath = '') {
    let html = '';

    for (const key in obj) {
      const currentPath = parentPath ? `${parentPath}/${key}` : key;

      if (typeof obj[key] === 'object' && Object.keys(obj[key]).length > 0) {
        // If the value is an object and not empty, create a nested div
        html += `
		<details>
          	<summary><a href="/${currentPath}">${key}</a></summary>
            <ul>
              ${createHtmlList(obj[key], currentPath)}
            </ul>
          </details>
        `;
      } else {
        // If the value is not an object or empty, create a clickable list item
        html += `<li><a href="/${currentPath}">${key}</a></li>`;
      }
    }

    return html;
  }

	//const renderedList = `<ul>${renderNestedList(nestedFolders)}</ul>`;
	const renderedList = createHtmlList(nestedFolders);

</script>

<div class="container navbar">
	<div class="row">
		<div class="col-md-12">
			<h2>Pages</h2>
			{@html renderedList}
		</div>
	</div>
</div>
