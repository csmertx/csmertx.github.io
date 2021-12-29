=> gpg --gen-key   
=> mkdir ~/.mutt  
=> touch ~/.mutt/password  
=> vim ~/.mutt/password  
=> gpg -r myemail@email.com -e ~/.mutt/password  
=> edit out sensitive information  
=> vim ~/.muttrc  
```
++ source "gpg -d ~/.mutt/password.gpg |" 
```

**Sourced:** http://xmodulo.com/mutt-email-client-encrypted-passwords.html  
