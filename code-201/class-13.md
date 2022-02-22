# Class 13 Reading Notes

## Article [The Past, Present, and Future of Local Storage for Web Applications](http://diveinto.html5doctor.com/storage.html)

Persistent local storange is one of the ares where native client apps have an advantage over web apps. <br>
for native apps, the OS provides abstract layers for storing and retrieving app-specific data.  <br>
Web apps didn't use to do this but cookies were invented and can be used to store small amounts of data <br>
Some downsides to cookies:  <br>
1. cookeis are included with every HTTP request, slows down the web app by needlessly transmitting same data over and over
2. because of 1: its also sending data unencrypted over the internet 
3. cookies are limited to about 4kb of data (enough to slow down your app but not enough to be terribly useful)

What we really want is:
1. a lot of storage space
2. on the client
3. that persists beyond a page refresh
4. isnt transmited to the server

before html5 there were attempts but all of them were unsatisfactory. <br>

#### HTML5 storage
HTML5 storage is a way for web pages to store named key/value pairs locally, within the client web browser  <br>
like cookies, the data persists even after you navigate away from the website, close the tab, or exit the browser  <br>
unlike cookies the data is never trasmitted to the remote web server  <br>
and unlike all previous attempts at providing persistent local storage, its implemented natively in web browsers, meaning its available even when third-party browser plugins are not  <br>

From your JS code youll access this storage through "localStorage" object in the global window object 

#### Using HTML5 storage
you store data based on the named key and retrieve the data with the same key  <br>
the key is a string  <br>
the data can be any type in JS  <br>
data is still stored as a string  <br>
need to use parseInt or parseFloat to change data type  <br>
```js
interface Storage {
  getter any getItem(in DOMString key);
  setter creator void setItem(in DOMString key, in any data);
};

var foo = localStorage.getItem("bar");
// ...
localStorage.setItem("bar", foo);

var foo = localStorage["bar"];
// ...
localStorage["bar"] = foo;


interface Storage {
  deleter void removeItem(in DOMString key);
  void clear();
};

interface Storage {
  readonly attribute unsigned long length;
  getter DOMString key(in unsigned long index);
};
```

#### Tracking changes to the HTML5 storage area
if you want to keep track of when the storage area changes, you can trap the storage event.  <br>
the event is fired on the window object and setItem removeItem or clear() are called and are actually changing something. <br>

#### Limitations
We only have 5mb of stroage each origin gets by default <br>
and you cannot ask for more storage <br>

#### How does it work? 
Every time a change occurs within the game, we call this function:

```js
function saveGameState() {
    if (!supportsLocalStorage()) { return false; }
    localStorage["halma.game.in.progress"] = gGameInProgress;
    for (var i = 0; i < kNumPieces; i++) {
	localStorage["halma.piece." + i + ".row"] = gPieces[i].row;
	localStorage["halma.piece." + i + ".column"] = gPieces[i].column;
    }
    localStorage["halma.selectedpiece"] = gSelectedPieceIndex;
    localStorage["halma.selectedpiecehasmoved"] = gSelectedPieceHasMoved;
    localStorage["halma.movecount"] = gMoveCount;
    return true;
}


function resumeGame() {
    if (!supportsLocalStorage()) { return false; }
    gGameInProgress = (localStorage["halma.game.in.progress"] == "true");
    if (!gGameInProgress) { return false; }
    gPieces = new Array(kNumPieces);
    for (var i = 0; i < kNumPieces; i++) {
	var row = parseInt(localStorage["halma.piece." + i + ".row"]);
	var column = parseInt(localStorage["halma.piece." + i + ".column"]);
	gPieces[i] = new Cell(row, column);
    }
    gNumPieces = kNumPieces;
    gSelectedPieceIndex = parseInt(localStorage["halma.selectedpiece"]);
    gSelectedPieceHasMoved = localStorage["halma.selectedpiecehasmoved"] == "true";
    gMoveCount = parseInt(localStorage["halma.movecount"]);
    drawBoard();
    return true;
}

localStorage["halma.game.in.progress"] = gGameInProgress;
gGameInProgress = (localStorage["halma.game.in.progress"] == "true");

localStorage["halma.movecount"] = gMoveCount;

gMoveCount = parseInt(localStorage["halma.movecount"]);

```




