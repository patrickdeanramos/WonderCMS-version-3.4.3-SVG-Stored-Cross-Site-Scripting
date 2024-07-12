# WonderCMS-version-3.4.3-SVG-Stored-Cross-Site-Scripting

WonderCMS version 3.4.3 is vulnerable to stored cross-site scripting (XSS) during file uploads involving SVG files. This flaw allows attackers to execute scripts in the browsers of unsuspecting users. The attack is executed by uploading a specially crafted SVG file containing malicious scripts, which are then rendered by the browser.

Vulnerable Code:<br>
File: wondercms-main/index.php<br>
2781: public function uploadFileAction(): void<br>
2816: 'image/svg+xml',<br>

Reproduction: 
1. Log in to the admin page.
2. Click on 'Files' and upload the SVG file containing the malicious code.
3. Click 'Upload' and then click on the URL to trigger the stored XSS vulnerability.

