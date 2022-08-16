# Steps to Reproduce

1. `npm ci`
2. `npm start`
3. Open Safari.
4. Navigate to `http://localhost:3000`.  (You should see a stripped out version of the demo rich text editor from the Slat website.)
5. Highlight the text that reads "Add all styles to me" and apply the first four styles by clicking on the corresponding buttons along the top of the web page.
6. Place the cursor at the end of the text.
7. Backspace all the text and slow down when there's nearly none left.
8. Backspace the last character.  You should see that the place holder text appears "Enter some rich text...".  **You might want to open the DOM inspector for the next step.**
9. Backspace again.  Note that the place holder text disappears.  If you have the inspector open, then note that the editable element(s) were deleted from the DOM.  **Now open the console in the dev tools.**
10. Type a few characters.  Note that an error is generated each time you type a character.  e.g.
```
[Error] Error: Cannot resolve a Slate point from DOM point: [object HTMLDivElement],0
	toSlatePoint (bundle.js:45025:89)
	toSlateRange (bundle.js:45082)
	(anonymous function) (bundle.js:47526)
```

Repeat this process without applying styles for the place holder text to remain in-tact(as expected).
