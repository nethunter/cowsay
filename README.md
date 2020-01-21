# cowsay
Modernized version of cowsay

This is a fork of https://github.com/piuccio/cowsay with these improvements:

* No reading files at runtime. Cows are declared as static compile-time dependencies.
* Works the same whether client-side or server-side, and whether running from
  raw source for from a transpiled bundle.
* Leveraging modern language features like destructuring and arrow functions.
* Update to more modern Javascript style with two-space indents, single quoted
  strings, and `const` and `let` instead of `var`, as you might see on the Google
  or airbnb JS style guides.

### Usage

See test/example.js for examples, but the basic usage is:

    cowsay.say('What you want to say');

Or pass some options:

    cowsay.say('Advanced', { cow: someCow, mode: 'paranoid' });
    cowsay.say('A quick brown fox jumped over the lazy dog', { W: 15 });
    cowsay.think('I\'m looking sideways', { e: 'cc' });

Get a demo of all available cows with `node test/cows.js`, and get a demo of all
available modes with `node test/modes.js`. Get a general test demonstrating line wrapping
and whitespace handling at `node test/example.js`.

### Examples

    console.log(cowsay('hi'));
     ____
    < hi >
     ----

            \   ^__^
             \  (oo)\_______
                (__)\       )\/\
                    ||----w |
                    ||     ||


    console.log(cowsay.say("The static String.raw() method is a tag function of template literals. This is similar to the r prefix in Python, or the @ prefix in C# for string literals. (But it is not identical; see explanations in this issue.) It's used to get the raw string form of template strings, that is, substitutions (e.g. \${foo}) are processed, but escapes (e.g. \n) are not."));
     __________________________________________
    / The static String.raw() method is a tag  \
    | function of template literals. This is   |
    | similar to the r prefix in Python, or    |
    | the @ prefix in C# for string literals.  |
    | (But it is not identical; see            |
    | explanations in this issue.) It's used   |
    | to get the raw string form of template   |
    | strings, that is, substitutions (e.g.    |
    | ${foo}) are processed, but escapes (e.g. |
    \ ) are not.                               /
     ------------------------------------------

            \   ^__^
             \  (oo)\_______
                (__)\       )\/\
                    ||----w |
                    ||     ||


    const whale = require('./cows/whale');
    console.log(cowsay.say('Moo', { cow: whale }));
     _____
    < Moo >
     -----

       \
        \
         \
                    '-.
          .---._     \ .--'
        /       `-..__)  ,-'
       |    0           /
        --.__,   .__.,`
         `-.___'._\_.'