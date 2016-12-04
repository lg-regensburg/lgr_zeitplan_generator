# Tool: A Timetable generator for athletics events

### Motivation - Why do I need this?

Maybe you are in charge to generate a timetable for events. 
You already got a document where the data you need to put in the table is saved.
If the information fits in our format, which is described below, you can easily convert it into a schedule with our tool.
That will save your time for task which should be rather in your focus.

### Usage and Requirements

This tool uses HTML5, JavaScrip, JQuery, Bootstrap, Node.js and Electron.

#### Getting started

##### Use in browser
Just go down to ```/zeitplantool/index.html``` and open the file in your browser.
We recomment Google Chrome or Firefox.

##### Use as a desktop application with Electron
For that you need to install Node.js and Electron.

[Node.js](https://nodejs.org/en/download/)

[Electron](https://github.com/electron/electron)


Clone the timetable tool ```/zeitplantool``` and navigate to into this directory with the command line.
Once you are there you can simply call 

```electron .```

to run the app.

You can also create a desktop using 

```electron-packager <directory-to-put-the-code> <name-of-app> --version=1.3.9```

and run the app using the 'name-of-app.exe'


It's possible that those instructions above won't work for you. 

In this case please use the following links for further information about conventing the tool to an desktop application:

[Electron #1](http://tutorialzine.com/2015/12/creating-your-first-desktop-app-with-html-js-and-electron/)

[Electron #2](https://github.com/electron/electron/blob/master/docs/tutorial/quick-start.md)

[Electron Packager](https://github.com/electron-userland/electron-packager)

#### Requirements

The tool will ask you to upload a HTML file which contains the data of the table.
The data needs to be provided in ```p.ev1``` tags. 
Furthermore in those paragraphes there has to be the following structure:

1. First line 
  * __Categories__ separated by "," and "-", providing values like "Frauen", "Männer", "weiblich[e]" or "männlich[e]". More categories ar possible by using as separator the "+" using by this regex ```(U|W|M)\d\d```. Those will be used to create the columns of the table.
  * The rest of this line will be converted to the __discipline__ which is the cell content of the table
  
2. Second line
  * The __date__ valid to the regex ```(3[01]|[0-2]\d)[.](0\d|1[0-2])[.]20\d\d``` and beginning the second line with "Datum" will be the date of the event. The tool will create for each a day a separated table.
  * The __time__ valid to the regex ```([01]\d|2[0-3]):[0-5]\d```. The time will be the index of the rows.
  
#### Output

You will get a table in HTML as an output displayed.

This table you can simply save at your computer for further usage!