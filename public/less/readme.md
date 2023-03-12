You should follow the semantic naming in your HTML as is explained  https://maintainablecss.com/
Instead of loading a single big file for all pages, we recommend only include the styles of the element presented in the page. 
LESS takes care of this.

`base` folder is like a library of general codes that is not bound to any specific pages. If you compile it to css the result should be always and empty css file. can always. So you can always `import` base.less in any LESS files without adding any load to the out file css file. 

`theme` folder contains the look and feel of the website and is the one that you need to update to match the theme of your website. .

You mostly create style for web pages. You will create a less file for each pages. If there are many pages, you mage come up with some additional sub-folderS or storing less files next to the corresponding html (template e.g. twig) files. 

If you have emails that you want to style, you will create a less file for each email template too. 

`base/widgets` is for reusable UI elements. Like accordions, tabs, checkboxes. They mostly take care of the auxiliary HTML elements that are needed to create those widgets. If you need to change them because of you site design better to add the changes to a new file in the theme folder. 

If your website hs more than one theme, rename them folder to `themes` and create a folder for each them and put them all in the 'themes' folder.

Test
====
Run the following and make sure the generated file is empty

```bash
lessc theme/theme.less temp.css
```