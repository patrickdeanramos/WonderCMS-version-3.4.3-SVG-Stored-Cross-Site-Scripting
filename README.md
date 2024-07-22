# WonderCMS-version-3.4.3-SVG-Stored-Cross-Site-Scripting

WonderCMS version 3.4.3 is vulnerable to stored cross-site scripting (XSS) during file uploads involving SVG files. This flaw allows attackers to execute scripts in the browsers of unsuspecting users. The attack is executed by uploading a specially crafted SVG file containing malicious scripts, which are then rendered by the browser.

<B>Vulnerable Code:</B><br>
File: wondercms-main/index.php<br>
2781: public function uploadFileAction(): void<br>
2816: 'image/svg+xml',<br>

<B>Reproduction:</B> 
1. Log in to the admin page.
2. Click on 'Files' and upload the SVG file containing the malicious code.
   ![alt text](https://github.com/patrickdeanramos/WonderCMS-version-3.4.3-SVG-Stored-Cross-Site-Scripting/blob/main/wondercms-svg-1.png?raw=True)
4. Click 'Upload' and then click on the URL to trigger the stored XSS vulnerability.

<B>Remediation</B><br>
https://github.com/WonderCMS/wondercms/issues/56

Authors:<br>
Patrick Dean Ramos<br>
Nathu Nandwani<br>
Junnair Manla<br>
Kevin Rosales<br>


