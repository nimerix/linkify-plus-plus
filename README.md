Linkify Plus Plus
=================
An userscript which can linkify almost everything. Based on Linkify Plus.

See also [linkify-plus-plus-core](https://github.com/eight04/linkify-plus-plus-core).

Features
--------
* Detect text url and convert them into links.
* Support dynamic content.
* Support unicode characters.
* Support custom rules.
* Custom whitelist, blacklist.
* Embed images.

You can find the configuration from greasemonkey menu.
![Greasemonkey Menu](https://i.imgur.com/tOTr7ys.jpg)

Installation
------------
[Greasy Fork](https://greasyfork.org/scripts/4255-linkify-plus-plus).

Testcase
--------
* <https://rawgit.com/eight04/linkify-plus-plus/master/demo/demo.html>
* <https://rawgit.com/eight04/linkify-plus-plus/master/demo/demo-large-content.html>

Configure
---------
### Match 4 digits IP
Always linkify IP even if the URL dosn't contains protocol and path.

### Embed images
If the url ends with `jpg|png|gif|jpeg`, create an image object and insert into link.

### Allow non-ascii character
Let url match unicode characters. (e.g. `http://www.bücher.ch`)

### Open link in new tab
Add `target="_blank"` to linkified links.

### URL must be surrounded by whitespace
Never linkify URLs concatenated with other words.

### Boundary characters between whitespace and URL
Only works if `URL must be surrounded by whitespace` is checked.

### Do not linkify these elements. (CSS selector)
If an element match the selector, LPP will skip the element.

### Always linkify these elements, override above. (CSS selector)
If an element match the selector, LPP will always linkify them, even the parent node is skipped.

### Max execution time (ms)
The script will terminate if it processes too long.

### Max script run time (ms)
Split process into small chunks to prevent hanging the browser.

### Custom rules
A list of regex pattern that will be likified, which is aimed to linkify non-http links. For example:
```
magnet:\?xt=\S+
evernote:///\S+
```

Changelog
---------
* Version 8.0.2 (Mar 4, 2017):
	- Update linkify-plus-plus-core to 0.2.0.
	- Fix blocking bug.
* Version 8.0.1 (Feb 26, 2017):
	- Fix global leaking bug in Tampermonkey.
* Version 8.0.0 (Feb 24, 2017):
	- Rewritten: the core logic is splitted out as [linkify-plus-plus-core](https://github.com/eight04/linkify-plus-plus-core).
* Version 7.4.4 (Feb 19, 2017):
	- Fix: protocol must start with letters.
* Version 7.4.3 (Feb 4, 2017):
	- Fix: some js object properties becomes valid TLDs.
	- Switch to inline-js.
	- Update TLDs.
* Version 7.4.2 (Dec 20, 2016):
	- Fix: drop String.includes to support FF38. [something broke](https://greasyfork.org/zh-TW/forum/discussion/13387/x)
* Version 7.4.1 (Dec 7, 2016):
	- Fix: empty custom rule bug.
* Version 7.4.0 (Dec 7, 2016):
	- Refactor. Add standalone and boundary options.
	- Add 4 digit IP option.
	- Use TLDs count from domaintools. Remove TLDs whose count <= 2.
* Version 7.3.1 (Nov 8, 2016):
	- Update include/exclude rules.
	- Update TLD list.
* Version 7.3.0 (Apr 2, 2016):
	- Support custom rules.
	- Fix leading `_` bug.
* Version 7.2.0 (Feb 15, 2016):
	- Don't use mutations if the size is too large.
	- Update TLDs.
* Version 7.1.0 (Jan 9, 2016):
	- Fix performance issue with mutations.
* Version 7.0.0 (Jan 5, 2016):
	- Completely rewrite. The linkification could be stopped during each links.
	- Fix performance issue on big text. [Try it yourself](https://rawgit.com/eight04/linkify-plus-plus/master/demo/demo-large-content.html).
	- Add `Max execution time` option.
	- Replace `ignoreClasses`, `ignoreTags` with CSS selector.
	- Limit document.contentType to `text/html` or `text/plain`.
* Version 6.2.1 (Oct 7, 2015):
	- Update excluding list, TLDs.
* Version 6.2.0 (Sep 5, 2015):
	- Use newest TLDs.
* Version 6.1.0 (Jul 14, 2015):
	- Enhance: strip BBCode.
	- Enhance: strip trailing question mark.
* Version 6.0.1 (Jul 3, 2015):
	- Add alt attribute to image.
* Version 6.0.0 (Jul 3, 2015):
	- Enhance: use ES6 generator.
	- Fix hanging bug in observer.
	- Fix lastIndex issue in createRE.
	- Remove config.log.
* Version 5.0.1 (Jun 21, 2015):
	- Add compatibility info.
	- Fix IN_QUE counting bug.
* Version 5.0.0 (Jun 21, 2015):
	- Fix url regex: add valid characters `'[]`.
	- Enhance traverser: use TreeWalker to parse DOM tree.
	- Enhance white-list: use multiple CSS selectors to specify valid nodes.
	- Enhance black-list: be able to remove built-in filter.
	- Enhance stripSingleParens: support brackets.
	- Add an option to use non-ascii characters in url.
	- Remove embedding function. Use [Embed Me!](https://greasyfork.org/zh-TW/scripts/10481-embed-me) instead.
	- Update GM_config to 2.0.2.
* Version 4.0.1 (May 8, 2015):
	- Fix SVGAnimatedString issue.
* Version 4.0.0 (Apr 27, 2015):
	- LPP don't remove `<wbr>` anymore. Use `Range` to select text.
* Version 3.6.3 (Apr 26, 2015):
	- Add `word-wrap: break-word`.
* Version 3.6.2 (Apr 26, 2015):
	- Change how tlds work.
* Version 3.6.1 (Apr 23, 2015):
	- Use regex to detect angular source.
* Version 3.6.0 (Apr 21, 2015):
	- Move embeding function out of LPP core.
* Version 3.5.1 (Apr 17, 2015):
	- Use better regex to detect image.
* Version 3.5.0 (Apr 16, 2015):
	- Use a different GM_config library.
* Version 3.4.2 (Apr 16, 2015):
	- Add spreadsheetinfo to ignore list.
* Version 3.4.1 (Apr 16, 2015):
	- Fix className issue. Move CSS rule to style.css.
* Version 3.4.0 (Apr 13, 2015):
	- New feature: Embed youtube video.
* Version 3.3.0 (Apr 1, 2015):
	- New feature: Open link in new tab.
* Version 3.2.6 (Apr 1, 2015):
	- Tampermonkey dosn't support magic TLD.
* Version 3.2.5 (Feb 20, 2015):
	- Make path match "," character.
* Version 3.2.4 (Jan 30, 2015):
	- Make user part of url match "-+" characters.
* Version 3.2.3 (Jan 21, 2015):
	- Fix parentNode == null bug in validRoot().
* Version 3.2.2 (Jan 9, 2015):
	- Fix root node validation bug.
* Version 3.2.1 (Jan 9, 2015):
	- Fix class matching bug.
* Version 3.2.0 (Dec 20, 2014):
	- Add `config.generateLog` option to config.
* Version 3.1.1 (Dec 5, 2014):
	- Add `https?://www.google.tld/webhp*` to excluding list.
* Version 3.1.0 (Nov 15, 2014):
	- Remove removeWBR(). Now the script will check `wbr` when traversing DOM.
* Version 3.0.6 (Nov 15, 2014):
	- Fixed potential bug that root could be invalid after removing `<wbr>`.
* Version 3.0.5 (Nov 14, 2014):
	- Fixed tag name excluding bug.
* Version 3.0.4 (Nov 14, 2014):
	- Add style.
* Version 3.0.3 (Nov 14, 2014):
	- Fixed comment element bug.
* Version 3.0.2 (Nov 14, 2014):
	- Fixed traverse bug.
* Version 3.0.1 (Nov 14, 2014):
	- Cleanup console.log.
* Version 3.0.0 (Nov 14, 2014):
	- Breaking change. Removed linkifyContainer and use new DOM traversal method.
* Version 2.4.3 (Nov 7, 2014):
	- Add custom class name black-list.
* Version 2.4.2 (Nov 7, 2014):
	- Add .bdsug to ignore list.
* Version 2.4.1 (Nov 7, 2014):
	- Ignore if @contenteditable attribute is true.
* Version 2.4.0 (Nov 7, 2014):
	- Add class whitelist. Set your cutom whitelist in config dialog.
* Version 2.3.25 (Nov 7, 2014):
	- Fix wbr removing bug.
* Version 2.3.24 (Nov 5, 2014):
	- Fix parenthesis match point.
* Version 2.3.23 (Nov 5, 2014):
	- Add parenthesis support.
* Version 2.3.22 (Oct 20, 2014):
	- Add ".brush:" to ignore list.
* Version 2.3.21 (Sep 30, 2014):
	- Fix: max node limits...
* Version 2.3.20 (Sep 29, 2014):
	- Enhance: Increase performance.
* Version 2.3.19 (Sep 29, 2014):
	- Fix: Reduce node limits.
* Version 2.3.18 (Sep 18, 2014):
	- Fix: Add h* tags into ignore list.
* Version 2.3.17 (Sep 16, 2014):
	- Enhance: Delay the script execution if there are too many nodes.
* Version 2.3.16 (Sep 15, 2014):
	- Enhance: Use better config style.
* Version 2.3.15 (Sep 15, 2014):
	- Fix: Grant bug (again)
* Version 2.3.14 (Sep 15, 2014):
	- Add: GM_config. Deside whether to display image.
* Version 2.3.13 (Sep 15, 2014):
	- Fix: Remove <wbr> before linkify.
* Version 2.3.12 (Sep 9, 2014):
	- Fix: Angular conflict. Check "{{ }}" pairs.
* Version 2.3.11 (Sep 7, 2014):
	- Enhance: add isIP function.
* Version 2.3.10 (Sep 7, 2014):
	- Enhance: Use better ip detection
* Version 2.3.9 (Sep 7, 2014):
	- Fix: Add domain check for ip numbers.
	- Fix: Add domain check ".." invalid.
* Version 2.3.8 (Sep 6, 2014):
	- Fix: Push to event queue to avoid Angular conflict. It should work on most of pages.
* Version 2.3.7 (Sep 6, 2014):
	- Fix: Match port and hyphen in domain.
* Version 2.3.6 (Sep 4, 2014):
	- Fix: Angular conflict.
* Version 2.3.5 (Sep 3, 2014):
	- Remove image when loading failed.
	- Remove debug code.
* Version 2.3.4 (Sep 3, 2014):
	- Since FF 32 have some problem dealing with unicode, use a new path RE.
* Version 2.3.3 (Sep 2, 2014):
	- Add svg and some new tags to ignore list.
* Version 2.3.2 (Sep 2, 2014):
	- Add ttp:// -> http:// alia.
	- Use TLD list!
* Version 2.3.1 (Sep 1, 2014):
	- Move class tester into xpath.
* Version 2.3 (Sep 1, 2014):
	- Match to a pretty large set. Check readme for detail.
* Version 2.2.2 (Aug 26, 2014):
	- Add .code to ignore list.
* Version 2.2.1 (Aug 17, 2014):
	- Ignore .highlight container.
* Version 2.2 (Aug 15, 2014):
	- Add images support.
	- Use Observer instead of DOMNodeInserted.
* Version 2.1.4 (Aug 12, 2012):
	- Bug fix for when (only some) nodes have been removed from the document.
* Version 2.1.3 (Oct 24, 2011):
	- More excludes.
* Version 2.1.2:
	- Some bug fixes.
* Version 2.1.1:
	- Ignore certain "highlighter" script containers.
* Version 2.1:
	- Rewrite the regular expression to be more readable.
	- Fix trailing "." characters.
* Version 2.0.3:
	- Fix infinite recursion on X(HT)ML pages.
* Version 2.0.2:
	- Limit @include, for greater site/plugin compatibility.
* Version 2.0.1:
	- Fix aberrant 'mailto:' where it does not belong.
* Version 2.0:
	- Apply incrementally, so the browser does not hang on large pages.
	- Continually apply to new content added to the page (i.e. AJAX).
* Version 1.1.4:
	- Basic "don't screw up xml pretty printing" exception case
* Version 1.1.3:
	- Include "+" in the username of email addresses.
* Version 1.1.2:
	- Include "." in the username of email addresses.
* Version 1.1:
	- Fixed a big that caused the first link in a piece of text to be skipped (i.e. not linkified).
