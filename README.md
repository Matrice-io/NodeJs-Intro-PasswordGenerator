
## 🔒 Password manager

1. Create a simple `pass.js` CLI tool to let user store/retrieve passwords stocked in a local file (e.g. in `~/.password-store`) as plain text/JSON.

2. Use a master password to encrypt/decrypt the file at each command using [`crypto`](https://nodejs.org/api/crypto.html) module (the [MDN documentation](https://developer.mozilla.org/en-US/docs/Web/API/Web_Crypto_API) of the homolog browser API is maybe more readable), the master password could be given as an `SECRET` [environment variable](https://nodejs.dev/learn/how-to-read-environment-variables-from-nodejs) like: `SECRET=barbapapa@93 ./pass.js github.com`

**BONUS:**

- Add a `generate` command that take advantage of the previous _password generator_ and store the password generated ;

- Use [GPG](https://en.wikipedia.org/wiki/GNU_Privacy_Guard) (you can directly [call](https://nodejs.org/api/child_process.html#child_processexeccommand-options-callback) `gpg` binary) to reproduce the behavior of zx2c4's [pass](https://www.passwordstore.org/) ;

- [Publish](https://docs.npmjs.com/cli/v8/commands/npm-publish) it on https://www.npmjs.com/ and make it works with [`npx`](https://www.npmjs.com/package/npx).
