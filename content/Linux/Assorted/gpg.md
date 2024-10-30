---
title: 💻 GnuPG
author: Chris Schammert (csmertx -- Christopher Schammert)
published: 2023-01-30
weight: -20
---

<br />

## Create New Key

- ```gpg –-gen-key```

## Encrypt File

- ```gpg -e -r $USER /dir/examplefile```

## Decrypt File

- ```gpg -d -o /dir/examplefile /dir/examplefile.(gz.)gpg```

- ```shred /dir/examplefile```
- ```rm /dir/examplefile```

## Encrypt/Decrypt Folder(s)

- First convert the folder(s) to file

- ```tar czf /dir/examplefolder.gz /dir/examplefolder```

- Then follow steps to encrypt/decrypt files

## One or more PGP Signatures could not be verified!
- ```gpg --recv-key [key]```

    > Key is usually printed with error message

## Export Local key

- ```gpg --list-keys # Target == examplekey```

- ```gpg --output mygpgkey_pub.gpg --armor --export examplekey```

- ```gpg --output mygpgkey_sec.gpg --armor --export-secret-key examplekey```

## Import Local key

- ```gpg --import ~/mygpgkey_pub.gpg```

- ```gpg --allow-secret-key-import --import ~/mygpgkey_sec.gpg```

- ```gpg --list-keys # to verify```

- ```rm mygpgkey\_{pup,sec}.gpg```

## Export/Import All Secret keys

- ```gpg --export-secret-keys > unique_name.asc```

- ```gpg --import unique_name.asc```

## Renew Expiration Date

- ```gpg --list-keys```

- ```gpg --edit-key [expiredkey]```

    - ```gpg> expire 1yr```

        > 1yr # or whatever is required.  This is for key 0

- Select subkeys too: key 1 # etc.

## Resources

- [The GNU Privacy Guard (Homepage)](https://gnupg.org/)

- [RedHat: Getting started with GPG (GnuPG)](https://www.redhat.com/sysadmin/getting-started-gpg)