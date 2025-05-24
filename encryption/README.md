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

#### And then later decrypt
sops decrypt -i secrets.json

SOPS_AGE_KEY_FILE="~/.config/mise/age.txt
