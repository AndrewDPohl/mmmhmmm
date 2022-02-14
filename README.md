# mmmhmmm challenge

## Bugs Found While Testing

 1. “X” doesn’t work when you try to close the ‘add a book’ feature (Console is throwing a message of “exiting to home”, but the view does not change - I would check the function being called and make sure that it is set up correctly, add a unit test)
![shown here](https://i.imgur.com/VNPS0wT.png)
 2.   Book Cover image is not loading (400 error when loading the image - possibly an issue with retrieving the correct url from the database and parsing it correctly, or may not be added to the src correctly?)
![shown here](https://i.imgur.com/nTv7m7p.png)
 3.   Book cover image is not in the correct placement (CSS position: absolute, width:0px, height: 9px; - turning those off positioned it correctly)
![shown here](https://i.imgur.com/SfrXSTg.png)
 4.   Trash icon is not correct (could just be that they didn't have the exact same icon available??)
 5.   Clicking the Trash icon does not successfully DELETE the book (401 Unauthorized error happening)
 6.   “Add Book” should be “Save” (according to Figma)
 7.   Font on the forms should have “font-weight: bold;” applied (per the Figma design)
![shown here](https://i.imgur.com/u8ekY8L.png)
 8.   “Add a new book” is spilling over too far too the left (possibly add padding-left: 15px on the h1, and then kill the padding on the “X” button)
 9.   P tag with class “Book_author” should have a smaller font size, and should have a font-color closer to #b9b4b4 (per the Figma design)
 10.   P tag with class “Book_description” should have a slightly larger font size (based on what I see in Figma)
 11.   “Description” form-field should be about 2-3 times taller than the other fields (this is going off of the Figma design; perhaps give it it’s own class or id and give it it's own height?)
![shown here](https://i.imgur.com/kLQNLRt.png)
 12.   When you add a new book, it doesn’t take you back to the list of books, it just empties the fields (not sure if this is expected or not, but it doesn’t seem like that would be the natural flow)
 13.   Background color of the main page seem incorrect (based on what I see in Figma, it should be more of a white)
 14.   Other things noticed: 
         1. App didn’t seem to work consistently: Adding books sometimes failed, in multiple browsers (Safari especially)
         2. Had to open up incognito window to get it to work on any kind of consistent basis).
         3. The page seems to be not responsive (but not sure if this is a requirement)


## Test Plan

  1. Open index page, verify that text is correct
  2. Click on “Add Book” and verify that it takes you to the form to add a book
  3. Verify that fields all look correct and to spec
  4. Enter values for the form, and click the “Save” button (ensure no errors or logging indicating of errors)
  5. Go to the index page and verify that the book displays (making sure that image is showing, text is all displayed in the proper color, font, font-size, etc)
  6. Check the network tab for the `books` call and see that the local data object of “books” has updated with the correct information
  7. Repeat steps 2-6 at least 2 more times using different images to make sure there won’t be any issues with different image sources
  8. Try deleting any of the books you’ve added (check the console for any errors or logging as this is being done)
  9. Verify that the book has been deleted by going back to the Home Screen verifying that it is no longer present (also check the network tab in the ‘books’ call to verify that it as been deleted from the database
