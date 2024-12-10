# Pepys Annotation Filter

A simple bookmarklet to collapse or filter annotations on [PepysDiary.com](https://www.pepysdiary.com).

## Features

- Collapse annotations from contributors you wish to ignore.
- Customize the list of excluded contributors.
- Easy to install and modify.

## Installation

1. Ensure the bookmarks bar in your browser is visible (<kbd>Ctrl</kbd>+<kbd>Shift</kbd>+<kbd>B</kbd>).
2. Copy the following code:
   ```javascript
   javascript:(function(){const excludedNames=["Robert Gertz","in Aqua Scripto"];document.querySelectorAll("#annotations%20article").forEach((e=>{const r=e.querySelector(".media-body"),t=document.createElement("details"),n=document.createElement("summary"),a=r.querySelector("h3.media-heading"),l=a.querySelector("span").innerText.trim();excludedNames.includes(l)||(t.open=!0),n.appendChild(a),t.appendChild(n);Array.from(r.querySelectorAll("p")).forEach((e=>t.appendChild(e))),r.innerHTML="",r.appendChild(t)}));})();
   ```
3. Right-click on the bookmarks bar and select "Add Bookmark" (or equivalent).
4. Name the bookmark "Toggle Annotations" (or a name of your choice).
5. Paste the code into the URL field of the bookmark.
6. Save the bookmark.

## Customization

1. Right-click on the bookmark and select "Edit Bookmark" (or equivalent).
2. Locate the `excludedNames` array in the code. It is a list of names enclosed in square brackets, e.g., `["Robert Gertz","in Aqua Scripto"]`. Add new names by placing them inside quotation marks and separating them with commas, or remove existing names by deleting them from the list.
3. Save your changes to update the bookmark.

## Usage

1. Visit an annotations page on [pepysdiary.com](https://www.pepysdiary.com).
2. Click the bookmarklet to toggle annotations based on your preferences.

## License

This project is licensed under the [MIT License](LICENSE).
