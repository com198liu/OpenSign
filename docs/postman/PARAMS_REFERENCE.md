# Cloud Function parameter templates (inferred from source)

## signPdf
- Required (inferred/manual): `(none detected)`
- Params seen: `docId, isCustomCompletionMail, mailProvider, pdfFile, signature, userId`

## sendmailv3
- Required (inferred/manual): `(none detected)`
- Params seen: `bcc, certificatePath, extUserId, filename, from, html, pdfName, recipient, replyto, subject, text, url`

## usersignup
- Required (inferred/manual): `(none detected)`
- Params seen: `userDetails`

## SendOTPMailV1
- Required (inferred/manual): `(none detected)`
- Params seen: `TenantId, docId, email`

## AuthLoginAsMail
- Required (inferred/manual): `(none detected)`
- Params seen: `email, otp`

## getUserId
- Required (inferred/manual): `username`
- Params seen: `email, username`

## getUserDetails
- Required (inferred/manual): `email, userId`
- Params seen: `email, userId`

## getDocument
- Required (inferred/manual): `docId`
- Params seen: `docId, include`

## getDrive
- Required (inferred/manual): `docId`
- Params seen: `docId, limit, skip`

## getReport
- Required (inferred/manual): `(none detected)`
- Params seen: `limit, reportId, searchTerm, skip`

## getTemplate
- Required (inferred/manual): `(none detected)`
- Params seen: `templateId`

## verifyemail
- Required (inferred/manual): `(none detected)`
- Params seen: `email, otp`

## getsignedurl
- Required (inferred/manual): `(none detected)`
- Params seen: `docId, templateId, url`

## batchdocuments
- Required (inferred/manual): `(none detected)`
- Params seen: `Documents`

## linkcontacttodoc
- Required (inferred/manual): `(none detected)`
- Params seen: `company, docId, email, jobTitle, name, phone`

## isextenduser
- Required (inferred/manual): `(none detected)`
- Params seen: `email`

## getlogobydomain
- Required (inferred/manual): `(none detected)`
- Params seen: `domain`

## addadmin
- Required (inferred/manual): `(none detected)`
- Params seen: `userDetails`

## checkadminexist
- Required (inferred/manual): `(none detected)`
- Params seen: `(none)`

## updateuserasadmin
- Required (inferred/manual): `(none detected)`
- Params seen: `email, masterkey`

## newsletter
- Required (inferred/manual): `(none detected)`
- Params seen: `domain, email, name`

## getteams
- Required (inferred/manual): `active`
- Params seen: `active`

## getcontact
- Required (inferred/manual): `(none detected)`
- Params seen: `contactId`

## updatecontacttour
- Required (inferred/manual): `(none detected)`
- Params seen: `contactId`

## declinedoc
- Required (inferred/manual): `docId, userId`
- Params seen: `docId, reason, userId`

## gettenant
- Required (inferred/manual): `contactId`
- Params seen: `contactId, userId`

## getsigners
- Required (inferred/manual): `(none detected)`
- Params seen: `search`

## savefile
- Required (inferred/manual): `fileName, fileBase64`
- Params seen: `fileBase64, fileName, id`

## savecontact
- Required (inferred/manual): `name, phone, tenantId`
- Params seen: `company, email, jobTitle, name, phone, tenantId`

## isuserincontactbook
- Required (inferred/manual): `(none detected)`
- Params seen: `(none)`

## updatetourstatus
- Required (inferred/manual): `(none detected)`
- Params seen: `ExtUserId, TourStatus`

## updatesignaturetype
- Required (inferred/manual): `(none detected)`
- Params seen: `SignatureType`

## updatepreferences
- Required (inferred/manual): `(none detected)`
- Params seen: `DateFormat, DownloadFilenameFormat, Is12HourTime, IsLTVEnabled, IsTourEnabled, NotifyOnSignatures, SendinOrder, SignatureType, Timezone`

## createduplicate
- Required (inferred/manual): `templateId`
- Params seen: `templateId`

## createbatchcontact
- Required (inferred/manual): `(none detected)`
- Params seen: `contacts`

## generatecertificate
- Required (inferred/manual): `docId`
- Params seen: `docId`

## fileupload
- Required (inferred/manual): `(none detected)`
- Params seen: `url`

## getuserlistbyorg
- Required (inferred/manual): `(none detected)`
- Params seen: `organizationId`

## editcontact
- Required (inferred/manual): `(none detected)`
- Params seen: `company, email, jobTitle, name, phone, tenantId`

## forwarddoc
- Required (inferred/manual): `(none detected)`
- Params seen: `docId, recipients`

## saveastemplate
- Required (inferred/manual): `docId`
- Params seen: `docId`

## updatetenant
- Required (inferred/manual): `(none detected)`
- Params seen: `details`

## recreatedoc
- Required (inferred/manual): `(none detected)`
- Params seen: `(none)`

## loginuser
- Required (inferred/manual): `email, password`
- Params seen: `email, password`

## adduser
- Required (inferred/manual): `name, email, password, organization, team, role, tenantId`
- Params seen: `email, name, organization, password, role, team, tenantId, timezone`

## filterdocs
- Required (inferred/manual): `(none detected)`
- Params seen: `caseSensitive, limit, skip`

## senddeleterequest
- Required (inferred/manual): `(none detected)`
- Params seen: `app`

## resetpassword
- Required (inferred/manual): `userId, password`
- Params seen: `password, userId`

## savesignature
- Required (inferred/manual): `(none detected)`
- Params seen: `id, initials, stamp, title, userId`

## managesign
- Required (inferred/manual): `(none detected)`
- Params seen: `id, initials, stamp, title, userId`

## getdefaultsignature
- Required (inferred/manual): `(none detected)`
- Params seen: `(none)`

## updateemailtemplates
- Required (inferred/manual): `tenantId, details`
- Params seen: `details`

## triggerevent
- Required (inferred/manual): `(none detected)`
- Params seen: `contactId, event`

## setwidgetpreferences
- Required (inferred/manual): `dateWidget`
- Params seen: `dateWidget`


## templatelist (REST classes endpoint)
- Method: `GET`
- URL: `{{parseBaseUrl}}/classes/contracts_Template?where={"IsArchive":{"$ne":true}}&order=-updatedAt&limit={{limit}}&skip={{skip}}&include=ExtUserPtr,CreatedBy,Signers,ExtUserPtr.TenantId,Bcc`
- Headers: `X-Parse-Application-Id`, `X-Parse-Master-Key` (optional `X-Parse-Session-Token`)
- Purpose: list templates with pagination.
