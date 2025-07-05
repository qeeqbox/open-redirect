<p align="center"> <img src="https://raw.githubusercontent.com/qeeqbox/open-redirect/main/content/open-redirect.svg"></p>

An application allows a user to control redirection to another URL. A threat actor may exploit that by sending a malicious redirect to a victim using the application, leading the victim to be sent to a malicious website controlled by the threat actor.

Clone this current repo recursively
```sh
git clone --recursive https://github.com/qeeqbox/default-credential
```
Run the webapp using Python
```sh
python3 default-credential/vulnerable-web-app/webapp.py
```
Open the webapp in your browser 127.0.0.1:5142
<p align="center"> <img src="https://raw.githubusercontent.com/qeeqbox/open-redirect/main/content/1.png"></p>
Right-click on the start icon and click Inspect from the menu. The icon has a hyperlink
<p align="center"> <img src="https://raw.githubusercontent.com/qeeqbox/open-redirect/main/content/2.png"></p>
Go to the network tab and then click on the star icon to see the network requests.
<p align="center"> <img src="https://raw.githubusercontent.com/qeeqbox/open-redirect/main/content/3.png"></p>
The redirect request was sent back to qeeqbox.com from the webapp. The client makes a new GET request to qeeqbox.com
<p align="center"> <img src="https://raw.githubusercontent.com/qeeqbox/open-redirect/main/content/4.png"></p>
A threat actor could send a malicious link, such as http://127.0.0.1:5142/redirect?url=http%3A%2F%2Fmalicious.xyz123, using social engineering attacks. If the victim falls for it, they will be redirected to the malicious website. If the victim clicks on update Firefox, they will install a malicious file
<p align="center"> <img src="https://raw.githubusercontent.com/qeeqbox/open-redirect/main/content/5.png"></p>

## Impact
Medium

## Names
- Open Redirect

## Risk
- Social Engineering
- Malware Distribution

## Redemption
- Input validation

## Require
- Social Engineering

## ID
cea84b63-1552-47ad-a160-503f1c913390
