
## 🔑 Password generator

0. Create a new project folder `password-generator`, then generate a `package.json` using the command `npm init` (and `git init` and commit each step of your work) ; create an empty `my_wonderful_program.js`, and make it print "Node rocks!" in the console when running `node my_wonderful_program.js`

1. Write a function that generate a random password, meaning a random string of characters (taking as argument the desired size of the password), do not hesitate to ask [SO](https://stackoverflow.com/questions/1349404/generate-random-string-characters-in-javascript) about it.

2. What about having instead the password copied to the clipboard without be printed on the screen? `npm install --save clipboardy` and import [`clipboardy`](https://www.npmjs.com/package/clipboardy), do you spot what change in your `package.json`?

3. Use [`yargs`](https://www.npmjs.com/package/yargs) (for CLI args parsing) to let user enable or not the previous option (password not displayed but copied in clipboard) with an `-c` argument. What about also taking as parameter the desired password length?

4. Add another option to require at least one symbol and/or one number in the generated password. And, when printing password on screen, display _symbols in blue_ and _numbers in red_ (using [ANSI code](https://en.wikipedia.org/wiki/ANSI_escape_code) by hand or importing a NPM module of your choice).

**BONUS** (at your option, use another method to generate password):

- the [XKCD style](https://xkcd.com/936/) (using a dict of words, you can find an English one [here](https://github.com/dwyl/english-words)) ;

- a [deterministic](https://www.rempe.us/strongpass/) method, that take a (website/app) name + a master password as input ;

- could we generate dictionary-based _easy to pronounce_ password? Yes, e.g. with [HMM](https://en.wikipedia.org/wiki/Hidden_Markov_model)!

## 🔒 Password manager

1. Create a simple `pass.js` CLI tool to let user store/retrieve passwords stocked in a local file (e.g. in `~/.password-store`) as plain text/JSON.

2. Use a master password to encrypt/decrypt the file at each command using [`crypto`](https://nodejs.org/api/crypto.html) module (the [MDN documentation](https://developer.mozilla.org/en-US/docs/Web/API/Web_Crypto_API) of the homolog browser API is maybe more readable), the master password could be given as an `SECRET` [environment variable](https://nodejs.dev/learn/how-to-read-environment-variables-from-nodejs) like: `SECRET=barbapapa@93 ./pass.js github.com`

**BONUS:**

- Add a `generate` command that take advantage of the previous _password generator_ and store the password generated ;

- Use [GPG](https://en.wikipedia.org/wiki/GNU_Privacy_Guard) (you can directly [call](https://nodejs.org/api/child_process.html#child_processexeccommand-options-callback) `gpg` binary) to reproduce the behavior of zx2c4's [pass](https://www.passwordstore.org/) ;

- [Publish](https://docs.npmjs.com/cli/v8/commands/npm-publish) it on https://www.npmjs.com/ and make it works with [`npx`](https://www.npmjs.com/package/npx).
