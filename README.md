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
## Email Configuration: Emails are sent through smtp with gmail
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


## Customized Email Templates:
As documented in TemplatesV2.docx

[This](https://forum.pkp.sfu.ca/t/shortcode-for-prepared-e-mails/10894/4) link documents all template variables available in OJS.

__NOTE:__ Any urls in the templates would need to be updated based on the journal's hosting environment.

KEY: SUBMISSION_ACK
```
SUBJECT: Submission Acknowledgement
BODY:
Re2: Received - {$contextName}
Dear {$authorName}:

{$submissionTitle}
We acknowledged receipt of your submission of the manuscript. Thank you for your considering WIJE to publish your work.
We will communicate with you once the peer review is complete. If you have any queries on your paper submission and review status, please kindly let us know.
Submission URL: {$submissionUrl}
Username: {$authorUsername}

```

KEY: REVIEW_REQUEST
```
SUBJECT: Article Review Request
BODY:
Re: Greetings - Invitation to Review an Article for WIJE
Dear {$reviewerName},
Ref: Manuscript entitled: {$submissionTitle}

Greetings.
You are cordially invited to review the captioned manuscript for The West Indian Journal of Engineering (WIJE).
We realise that our expert reviewers greatly contribute to the high standards of the Journal, and we thank you for your present and future participation.
We will be pleased to receive your review at your earliest convenience although it will be most helpful if the review can be completed by {$reviewDueDate}.
All communications regarding this manuscript are privileged. You will be anonymous at all times, unless you request otherwise, and any conflict of interest, suspicion of duplicate publication, fabrication of data or plagiarism should immediately be reported to us.
 
We have tried our best efforts to meet the tight publication schedule for the forthcoming Volume.  If you for any reasons are not able to review the manuscript, we would be grateful if you could kindly reply us by {$responseDueDate}.


We thank you in advance for evaluating this manuscript.  


```

KEY: SUBMISSION_UNSUITABLE

```
SUBJECT: Unsuitable Submission
BODY:

Dear {$authorName},
Re: Notification of Review Status - WIJE Paper {$contextName}
{$contextName}
On behalf of the Journal’s Publications and Editorial Board, we are sorry to inform you that your paper has not been accepted for possible publication at WIJE, with respect to the comments and suggestions from reviewer.
We attached the reviewers’ feedback and your submitted manuscript for your record. We thank you again for your consideration of publishing your research work at WIJE.

{$editorialContactSignature}

```

KEY: REVIEW_REMIND

```
SUBJECT: Submission Review Reminder
BODY:
Re**: Gentle Reminder: Review for the WIJE {$reviewerName}                              
Ref: {$submissionTitle}

This e-mail is a gentle reminder that your review for {$contextName} is due by {$reviewDueDate}. The authors are naturally anxious about the progress on the paper, and I would appreciate your help in expediting the review process
Please do not hesitate to contact us if you need any additional information.
If you do not have your username and password for the journal's web site, you can use this link {$passwordResetUrl} to reset your password (which will then be emailed to you along with your username). 

Submission URL: {$submissionReviewUrl}
{$editorialContactSignature}

```

KEY: EDITOR_DECISION_REVISIONS

```
SUBJECT: Editor Decision
BODY:
Re: Notification of Review Status for WIJE Paper

Dear Authors,
Paper entitled: {$submissionTitle}
On behalf of Journal’s Publications and Editorial Board, we would like to inform you that we have completed the peer-review of your paper submitted to {$contextName}. The paper has been marginally considered for possible inclusion in The West Indian Journal of Engineering, WIJE, subject to the satisfactory revision of the manuscript.   
 
We would be grateful if you could kindly reply us whether you would like to revise your paper for re-submission with respect to the reviewers’ comments and also the justification of the present paper submission.
 
We greatly appreciate your consideration of publishing your research work in this Journal.
 
With best wishes and regards,


{$editorialContactSignature}

```

KEY: REVIEW_REQUEST

```
SUBJECT: Article Review Request
BODY:
Re: Greetings - Invitation to Review an Article for WIJE
Dear {$reviewerName},
Ref: Manuscript entitled: {$submissionTitle}

Greetings.

You are cordially invited to review the captioned manuscript for The West Indian Journal of Engineering (WIJE).
We realise that our expert reviewers greatly contribute to the high standards of the Journal, and we thank you for your present and future participation.
We will be pleased to receive your review at your earliest convenience although it will be most helpful if the review can be completed by {$reviewDueDate}.
All communications regarding this manuscript are privileged. You will be anonymous at all times, unless you request otherwise, and any conflict of interest, suspicion of duplicate publication, fabrication of data or plagiarism should immediately be reported to us.
 
We have tried our best efforts to meet the tight publication schedule for the forthcoming Volume.  If you for any reasons are not able to review the manuscript, we would be grateful if you could kindly reply us by {$responseDueDate}.

We thank you in advance for evaluating this manuscript.  

```

KEY: EDITOR_DECISION_ACCEPT

```
SUBJECT: Editor Decision
BODY:
{$authorName}:

We have reached a decision regarding your submission to {$contextName}, "{$submissionTitle}".

Our decision is to: Accept Submission

{$editorialContactSignature}

```

KEY: REVIEW_REQUEST_SUBSEQUENT

```
SUBJECT: Article Review Request
BODY:
Dear {$reviewerName},
 
Ref: {$submissionTitle}
 
Following your comments on the above paper, the corresponding author has now submitted a revised manuscript. We would be most grateful if you could accept our invitation to serve for the second Stage of peer review and would please let us have your comments on the revision.
 
If for any reason that you may not be able to review the revised manuscript or are not willing to undertake the review, please kindly let us know as soon as possible. You may e-mail us with your reply.
  
The authors are naturally anxious about the progress on the paper, and we would appreciate your help in expediting the review process. We look forward to receiving your completed reviewer's report by {$reviewDueDate}
 
We thank you in advance for your assistance. We realise that our expert reviewers greatly contribute to the high standards of the Journal, and we thank you for your present and future participation.


 The web site is {$contextUrl}
Submission URL: {$submissionReviewUrl}

Best wishes and regards,
 
{$editorialContactSignature}


```