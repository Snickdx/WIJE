# West Indian Journal of Engineering Project


## Changes

Added project to git repo with the following changes from stock OJS (Commit [8fabe](https://github.com/Snickdx/WIJE/commit/8fabe1e2d68bf1c370f89402285cf89f74d619b9)):


* Added [bootstrap plugin theme](https://github.com/NateWr/bootstrap3#installation)
* Added static pages: About, Editorial Team, Submissions, Contact [etc](http://138.197.231.114/ojs/index.php/testj/management/settings/website)
* Altered [NavBar](https://github.com/Snickdx/WIJE/blob/master/plugins/themes/bootstrap3/templates/frontend/components/primaryNavMenu.tpl) to link to static pages 
```
      <li>
        <a href="http://snickdx.me/ojs/index.php/testj/advisors">
          International Advisory Committee
        </a>
      </li>
      <li>
        <a href="http://snickdx.me/ojs/index.php/testj/editorial">
          Editorial Board
        </a>
      </li>
      <li>
        <a href="http://snickdx.me/ojs/index.php/testj/staff">
          Editorial Sub Committee
        </a>
      </li>
```
Email Configuration: Emails are sent through smtp with gmail
On the gmail account: 
* allow less secure apps https://myaccount.google.com/lesssecureapps
* enable smtp https://mail.google.com/mail/u/0/#settings/fwdandpop
* Edit email settings in config.inc.php


_Notice_ : A domain must be registered on the hosting server along with SSL for email to work

```
;;;;;;;;;;;;;;;;;;
; Email Settings ;
;;;;;;;;;;;;;;;;;;

[email]

; Use SMTP for sending mail instead of mail()
smtp = On

; SMTP server settings
smtp_server = smtp.gmail.com
smtp_port = 465

; Enable SMTP authentication
; Supported mechanisms: ssl, tls
smtp_auth = ssl
smtp_username = address@gmail.com
smtp_password = password

; Allow envelope sender to be specified
; (may not be possible with some server configurations)
allow_envelope_sender = On

; Default envelope sender to use if none is specified elsewhere
default_envelope_sender = wiournalengineering@gmail.com
```


Email Templates:

```
```
