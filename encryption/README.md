### Encryption scratch / yes even private keys are commited here for reference

### Generate a keypair with age

```shell
    age-keygen -o ~/.config/mise/age.txt
    Public key: <public key>
```

This will print out a public key and store the private key in the specfied age file.

> Will encrypt the file with the public key
sops encrypt -i --age "<public key>" secrets.json

-i overwrites the file with the encrypted version (which is safe to commit)

#### And then later decrypt (this did not work for some reason)
sops decrypt -i secrets.json
SOPS_AGE_KEY_FILE="~/.config/mise/age.txt

Setting

This worked

file .env.json in root
with mise.toml

[env]
_.file = ".env.json"

age-keygen -o ~/.config/mise/age.txt
sops encrypt -i --age <public key> .env.json
MISE_SOPS_AGE_KEY=AGE-SECRET-KEY-oeuoeuoeuoeuoeuoeuue

mise.env

now env variables will be in envirnoment

eval "$(mise env -s bash)"

