<script>
	// @ts-nocheck

	let data = import.meta.glob("/src/routes/**/+page.md");
	let paths = data;

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

	function createHtmlList(obj, parentPath = "", depth = 0) {
		let html = "";

		for (const key in obj) {
			const currentPath = parentPath ? `${parentPath}/${key}` : key;

			if (
				typeof obj[key] === "object" &&
				Object.keys(obj[key]).length > 0
			) {
				// If the value is an object and not empty, create a nested div
				html += `
          	<li><h${depth + 3}><a href="/${currentPath}">${key}</a></h${
					depth + 3
				}></li>
            <ul>
              ${createHtmlList(obj[key], currentPath, depth + 1)}
            </ul>
        `;
			} else {
				// If the value is not an object or empty, create a clickable list item
				html += `<li><a href="/${currentPath}">${key}</a></li>`;
			}
		}

		return html;
	}

	//const renderedList = `<ul>${renderNestedList(nestedFolders)}</ul>`;
	let renderedList = createHtmlList(nestedFolders);
</script>

<div class="container navbar">
	<div class="row">
		<div class="col-md-12">
			<h2>Pages</h2>
			{@html renderedList}
		</div>
	</div>
</div>
