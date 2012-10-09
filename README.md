# CommonUtils

CommonUtils is a utility library for Java which provides common set of functionalities that are required in most of the web applications. Functions include, plaintext/file to hash-code generation, validating form fields, generating random [CAPTCHA](http://en.wikipedia.org/wiki/CAPTCHA) challenges, and many other stuff.

## Why CommonUtils?

I've been working on many Java web projects lately, and required these common set of functionalities in each of them, so I created this library for my usage, but its free and open source under terms of [GPLv3](http://www.gnu.org/licenses/gpl.html) so anyone can add new features to this and make it better.

## Platforms, Tools and Technologies used

* **IDE** - Eclipse 4.2
* **Java** - JDK 1.7 (to be available for JDK 1.6 too)

## Package Description

* `org.commonutils.util` - Classes for Form field validation and Mathematical CAPTCHA generation.
* `org.commonutils.security` - Classes for Forward Hash code generation ([MD5](http://www.ietf.org/rfc/rfc1321.txt) and [SHA-1](http://www.ietf.org/rfc/rfc3174.txt), for now).

## Usage

You can download **CommonUtils0.1.jar** from `dist` folder and include it into your project. CommonUtils provides two packages as of now, `org.commonutils.util` for Utility classes like Form fields validation and Mathematical CAPTCHA generation, and `org.commonutils.security` for forward hashing in **MD5** and **SHA-1**. While all the classes has Javadoc mentioned, following is the summary of classes and its methods that CommonUtils provides.

### **`org.commonutils.util.FieldValidator`**
***

This class provides set of functions to check for valid common form fields like, Alphabets, Numbers, Email Address, Phone numbers, Dates, Passwords, etc.

* **`FieldValidator()`** - Initializes this FieldValidator object without any custom pattern.
* **`FieldValidator(String pattern)`** - Initializes this FieldValidator object with custom pattern (Regular Expression).
* `boolean isPattern(String key) throws UndefinedPatternException` - Checks whether given String key matches with defined custom pattern. Throws `UndefinedPatternException` if no custom pattern was defined during object creation.
* `boolean isNumber(String key)` - Checks whether given String key is a valid number.
* `boolean isFloat(String key)` - Checks whether given String key is a valid floating point number.
* `boolean isAlphabet(String key)` - Checks whether given String key is a valid Alphabet.
* `boolean isDate(String key)` - Checks whether given String key is a valid Date. Valid format for Date is standard Indian date format, i.e. DD-MM-YYYY (where, allowed separators are `-` or `.` or `/`).
* `boolean isDate(String key, String formatpattern)` - Checks whether given String key is a valid Date as per given format pattern regex.
* `boolean isEmail(String key)` - Checks whether given String key is a valid Email address.
* `boolean isPhone(String key)` - Checks whether given String key is a valid Phone number. Valid phone number contains only numbers, a dash (-) and a plus sign (+), with no limits in length of number.
* `boolean isSimplePassword(String key)` - Checks whether given String key is a valid simple Password. Valid Simple password is at least 8 characters long with no restrictions on type of characters.
* `boolean isPassword(String key)` - Checks whether given String key is a valid Password. Valid Password must contain a minimum of one lower case character, one upper case character, one digit, one special character, and at least 8 characters long.
* `boolean isSentence(String key)` - Checks whether given String key is a valid Sentence. Valid sentence contains alphabets, numbers, a space, a comma and full-stop only.

### **`org.commonutils.util.MathChallengeCaptcha`**
***

This class provides random Mathematical challenge generation to implement CAPTCHA. It provides JSON String that has simple arithmetic expression (Eg; 2 * 5 = 10), where user must be provided with only operands and he's supposed to calculate the answer and provide it as input.

* **`public MathChallengeCaptcha() throws NoSuchAlgorithmException`** - Initializes this MathChallengeCaptcha object with 10 as maximum possible value of numbers used in generated challenge.
* **`MathChallengeCaptcha(int max) throws NoSuchAlgorithmException`** - Initializes this MathChallengeCaptcha object with provided maximum possible value of numbers used in generated challenge.
* `String getChallenge()` - Gets Mathematical Challenge as a JSON String that contains an expression values; operand1, operand2, operator and MD5 Hash code of answer.

### **`org.commonutils.security.MD5Hash`**
***

This class provides methods to calculate [MD5](http://www.ietf.org/rfc/rfc1321.txt) hash code of String or File.

* **`MD5Hash() throws NoSuchAlgorithmException`** - Initializes this MD5Hash object with MD5 algorithm and resets the digest.
* `String getStringHash(String key)` - Gets 32 character MD5 Hash String for the given key.
* `String getFileHash(File source) throws FileNotFoundException, IOException` - Gets 32 character MD5 Hash String for the given File.

### **`org.commonutils.security.SHA1Hash`**
***

This class provides methods to calculate [SHA-1](http://www.ietf.org/rfc/rfc3174.txt) hash code of String or File.

* **`SHA1Hash() throws NoSuchAlgorithmException`** - Initializes this SHA1Hash object with SHA-1 algorithm and resets the digest.
* `String getStringHash(String key)` - Gets 41 character SHA-1 Hash String for the given key.
* `String getFileHash(File source) throws IOException` - Gets 41 character SHA-1 Hash String for the given File.

## Version Information

* 0.1 - First Release.

## Author

[Kushal Pandya](https://github.com/kushalpandya)