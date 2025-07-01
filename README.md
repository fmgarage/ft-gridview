# FT GridView
Display records as a responsive grid in list view  with dynamic columns. Perfect for a photo lightbox or product catalog. 

The demo is set to display 3 to 6 columns depending on the window width. You can extend this by adding a calculation field and a relation for each extra column. 

This technique is using plain FileMaker, no plugins, JavaScript or WebViewers involved. Images are AI-generated using the ThisPersonDoesNotExist service. 

 ![5 Columns](docs/assets/screen5.png)

#### How Does It Work?

The demo uses a single list view that has no data part, only a leading sub summary. Depending on the window width the record position in the foundset by *Get(RecordNumber)* is quantized by the number of visible columns, so for example in a 3 column view 1-2-3-4-5-6 outputs to 1-1-1-2-2-2 and the list then is grouped by this value. Using individual relations to the next 1 to 5 records in the foundset are then used to display their image containers next to each other. 



#### Getting Started

Download the latest release and open it in FileMaker Pro. Klick "Add Records" and set the amount of records to reasonable number. Downloading the images will take a while but you can cancel by holding down the esc key. 

To implement the grid view into your own file you will have to add the *_cols*, *group_by* and *id_next\** fields to your table along with their relationsships. Then you add a list view layout with a leading subsummary part, sorted by the *group_by* field. The resize trigger for the layout uses the *sort* script that you will also have to copy.



#### Searching

There is a quickfind input where you can search for city or country. This is to demonstrate what is necessary when you alter the foundset. Cached values have to be cleaned and the sort script has to be called to display the grouped records. 



#### Sorting Records

I still have to figure this out. In theory records can be sorted by any criteria as long as the grouping order is maintained as the last criteria to activate the subsummary. Ideas welcome!



#### What does 'FT' stand for?

All our **FileMaker**-based projects and products are prefixed with an **F**, and the **T** is for **tools, technology, tipps&tricks, techniques** or open **templates** for the community. These files are basically examples and demos where you can copy stuff from and include it your own apps and solutions.

Browse all our FT repos: https://github.com/fmgarage?q=ft-

