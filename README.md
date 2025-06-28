# FT GridView
Display records as a responsive grid in list view  with dynamic columns. Perfect for a photo lightbox or product catalog. 



The demo is set to display 3 to 6 columns depending on the window width. You can extend this by adding a calculation field and a relation for each extra column. 

This technique is using plain FileMaker, no plugins, JavaScript or WebViewers involved. Images are AI-generated using the ThisPersonDoesNotExist service. 

 ![5 Columns](docs/assets/screen5.png)

### How Does It Work?

The list view has no data part, only a leading sub summary. Depending on the window width the record position in the foundset by *Get(RecordNumber)* is quantized to the actual number of visible columns, so for example in a 3 column view 1-2-3-4-5-6 outputs to 1-1-1-4-4-4 and the list is then grouped by this. Using individual relations to the next 1 to 5 records in the foundset are then used to display their image container next to each other. 
