# creditcard.js

JavaScript object that enables you to determine a credit card type by credit card number and validate a credit card number.

I needed a way to validate a credit card number and updated the code to an object with several methods to help validate a credit card form. I originally downloaded the code from John Gardner at [JavaScript Credit Card Validation Function](http://www.braemoor.co.uk/software/creditcard.shtml).

* I converted the code to an object.
* Added method to determine the credit card type by credit card prefix.
* Removed the requirement to supply the card type when validating a credit card number.

> The structure of credit card formats was gleaned from a variety of sources on the web, although the best is probably on [Wikepedia ("Credit card number")](http://en.wikipedia.org/wiki/Credit_card_number).
>
> John Gardner

## Usage

    <script src="path/to/creditcard.js"></script>

## Syntax

### creditCard.getType(cardNo, [includeCards])
Returns the name of the card based on a partial or complete credit card number. If the card is not found, undefined is returned. This can be used to display a credit card image next to the input field as the user types.

### creditCard.isValid(cardNo, [includeCards])
Validates the supplied credit card number. Returns false if invalid or not supported. Uses the card number prefix to determine the kind of card to check.

### creditCard.errMsg()
  Returns the text of the last error or an empty string if no error.

### creditCard.errNo()
Returns the last error number.

### creditCard.set(options)
Can be a string or an object. If a string it sets an internal list of supported credit cards. If an object, it can optionally set the supported credit cards or error message strings. The object can be in the following format.

    {
      supportedCards: "visa, mastercard, amex, discover",
      ccErrors: ["", "language or program specific errors", ...]
    }

## Parameters
### cardNo

Credit card number.

### includeCards (optional)

Optional list of credit cards to check in a comma delimited string. This is used if you only want to validate certain cards. ie. This string will cause all cards that are not in the list to return an error.

    creditcard.set("visa, mastercard, amex, discover");

returns true because the card number is a Discover card.

    creditcard.isValid("6011 0000 0000 0004", "visa, mastercard, amex, discover")

returns false because the card number is a Diners Club Carte Blanche card.

    creditcard.isValid("3000 0000 0000 04", "visa, mastercard, amex, discover")


## Parameters (No longer used, from original program.)
### cardnumber
number on the card

### cardName
name of card

## Browser Support

Tested in the latest versions of Chrome, Firefox, Safari, IE 5.5 - 11, iOS, and Android.

## Issues

Have a bug? Please create an [issue](https://github.com/tannyo/creditcard.js/issues) here on GitHub!

## Contributing

Want to contribute? Great! Just fork the project, make your changes and open a [pull request](https://github.com/tannyo/creditcard.js/pulls).

## Changelog
### Authored by John Gardner
* 01 Nov 2003 Created
* 26 Feb 2005 Additional cards added by request
* 27 Nov 2006 Additional cards added from Wikipedia
* 18 Jan 2008 Additional cards added from Wikipedia
* 26 Nov 2008 Maestro cards extended
* 19 Jun 2009 Laser cards extended from Wikipedia
* 11 Sep 2010 Typos removed from Diners and Solo definitions (thanks to Noe Leon)
* 10 Apr 2012 New matches for Maestro, Diners Enroute and Switch
* 17 Oct 2012 Diners Club prefix 38 not encoded

### Authored by Tanny O'Haley
* 20 Nov 2014 TKO Recoded as a javascript object.
* 21 Nov 2014 TKO
  1. Modified cards array to store regular expressions and numbers for length.
  2. Updated MasterCard and DinersClub prefixes from Wikipedia.
  3. Updated documentation.
  4. Cleaned up code.
* v0.10 24 Nov 2014 TKO Created in GitHub by Tanny O'Haley

## License

The MIT License (MIT)

Copyright (c) 2014 [Tanny O'Haley](http://tanny.ica.com) and [John Gardner](http://www.braemoor.co.uk/)

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
