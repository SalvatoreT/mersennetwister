# mersennetwister

The Mersenne Twister is a pseudo-random number generator invented by Makoto Matsumoto in 1997. Details can be found on the [Wikipedia page](http://en.wikipedia.org/wiki/Mersenne_twister) and on Matsumoto's [website](http://www.math.sci.hiroshima-u.ac.jp/~m-mat/MT/emt.html).

This implementation is based on Sean McCullough's [port](https://gist.github.com/banksean/300494) of the original C code written by Makato Matsumoto and Takuji Nishimura.

Improvements over Sean's version are

  - more idiomatic, [jshint](http://www.jshint.com/)-compliant and [jsdoc](http://usejsdoc.org/)-annotated code
  - unit tested
  - compatible with [Node.js](http://nodejs.org/), [requirejs](http://requirejs.org/)  and browser environments
  - available as an [npm](https://npmjs.org/), [Jam](http://jamjs.org/) and [Bower](http://bower.io/) module
 

### Installation

*coming soon*

### Usage

You can either just use the static `random` method of the module, which will return a random float just like [`Math.random`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Math/random) does. If desired you can also instantiate your own instance of the mersenne twister and use its methods:

    var mt = new MersenneTwister(seed); // if no seed is defined, seed randomly
    
    mt.int();    // random 32-bit integer
    mt.int31();  // random 31-bit integer
    
    mt.rnd();       // random float in the interval [0;1[
    mt.rndHiRes();  // random float in the interval [0;1[ with 53-bit resolution
    mt.real();      // random float in the interval [0;1]
    mt.realx();     // random float in the interval ]0;1[
    
    mt.init(seed);      // (re)seed the generator with an unsigned 32-bit integer
    mt.initArray(key);  // (re)seed using a state vector of unsigned 32-bit integers

Take a look at the inventor´s [website](http://www.math.sci.hiroshima-u.ac.jp/~m-mat/MT/emt.html) if more detailed information is required.

### Licensing
As indicated [here](http://www.math.sci.hiroshima-u.ac.jp/~m-mat/MT/MT2002/elicense.html), the Mersenne Twister algorithm is free to be used for any purpose, inclusing commercial use. The license file of this module contains the text found in the [C implementation](http://www.math.sci.hiroshima-u.ac.jp/~m-mat/MT/MT2002/CODES/mt19937ar.c) on which it is based.
