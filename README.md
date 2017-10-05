# ChessNotationLibraryAndroid
A chess notation library (.aar) for supporting chess notation in 56 languages. 


This is Version 1.0 (see version history at the bottom of this document)

Description and purpose of this library:

This is an Android library (compiled into an .aar file that you can import) for supporting localization in 56 different languages
to automatically the the correct symbols used for KQRBN in the current used language on the phone. It also supports figure notation.
The library will automatically use the primary language (also support for new API 24+) used on the phone to return the symbols used for that language. 
If the user has a non-supported language it will use English KQRBN as the default. Also non-latin languages like cyrillic and Tamil
are supported (using unicode). 
See the end of this document for a complete list of supported languages. The library uses the information about the letters for the
pieces from this source: https://en.m.wikipedia.org/wiki/Chess_piece

You can use the library for what you want. It would be nice to receive an email saying thanks or similiar at martinknud@gmail.com.
You can also write to that email to suggest features or point out problems or if you know the symbols used for non-supported languages.


Setting up the library in your Android Project:

1. Copy the .aar file into the /libs folder in Android Studio (that folder already exists - shift to the project view
in Android Studio and go in under your project name and you will see this folder).

2. Now go to the menu : File->New->New Module and then Choose "Import jar/aar package" and click the file opener button at the far-rigth
in the dialogue. Then navigate to the .aar file you copied into your project in step 1. 

3. Now go to your build.gradle for you main app module (not the project gradle)
   and put the following under the depencies {} section:     
   compile project(':chessnotationlibrary')


4. Compile your project again.

That's it!

Overview of the library

All the methods and constants are static in this class, so no need to create an object of the type ChessNotation.

The library has the following methods:
void init(Context context) : this sets up the library for use.
String getPiece(int piece) : This gets a string representing the piece in the currently selected language.
void setCurrentLanguage(String lang): This overrides the autodetected language. You can use the constants

Using the library:

The first thing is to initialize the library - which you should normally do in your onCreate for your main Activity.
You can simple now use the code completion on the library, so just type "ChessNotation." and use code completion to get the 
methods and constants. So put "ChessNotation.init(this);" in the onCreate method of your main activity - "this" refers to the activity itself.
This only need to be done once. 

Per default, the library will automatically then detect the primary language the user has set the phone to and then use the letters for KQRBN that are
used in this language. You can then simply use the constants defined (KING, QUEEN etc) to get the letter used for the local language:
String symbol = ChessNotation.getPiece(ChessNotation.QUEEN); //will return Q in English, D in Danish for instance.
56 language are supported including non-latin languages like russian, georgian etc etc. If no language can be found that matches the user, then
the library defaults to using KQRBN. 

You can also use the figure notation. Simple call setCurrentLanguage(ChessNotation.FIGURINE) and then you will get the figurines (using unicodes) in 
The parameter passed to setCurrentLanguage should be in the form of the 3-letter ISO code for that language.
See a list at : https://www.loc.gov/standards/iso639-2/php/code_list.php


Languages supported:
Figurine notation.
English

Afrikans
Albanian 
Armenian 
Basque language
Belarussian 
Bengali
Bulgarian
Catalan
Chinese
Czech
Danish
Dutch    
Esperanto
Estonian
Finnish
French
Georgian
German
Greek
Hindi
Hebrew
Hausa   
Hungarian  
Ido
Icelandic
Indonesian
Irish
Italian
Japanese
Javense
Korean
Latvian
Lithuanian
Luxenborgish
Malay
Marathi
Mongolian
Norweegian
Persian (farsi)
Polish
Portuguese
Romanian
Russian
Scotish (gaelic)
Sicilian
Slovakian
Slovenian
Spanish
Swedish
Tamil
Thai
Turkish
Ukrainian
Vietnamese
Welsh
      

Version History:
1.0 First public release.
 
