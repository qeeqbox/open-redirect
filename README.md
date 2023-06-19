<p align="center"> <img src="https://raw.githubusercontent.com/qeeqbox/open-redirect/main/open-redirect.png"></p>

A threat actor may send a malicious redirection request for a vulnerable target to a victim; the victim gets redirected to a malicious website that downloads an executable file

## Example #1
1. Threat actor crafts an email with a malicious redirection request for a vulnerable target and sends the email to a victim
2. The victim clicks on the email and sends the request to the vulnerable target
3. The target processes the malicious redirection request back to the victim
4. The victim's browser redirects the user to a malicious website

## Code
#### Target-Logic 
```js
app.post("/weclome", (request, response) => {
    if (request.redirect){
        res.redirect(req.query.redirect);
    } else {
        res.redirect("/")
    }
});
```

#### Target-In
```
?redirect=test.com
```

## Impact
Medium

## Names
- Open Redirect

## Risk
- Redirect users

## Redemption
- Input validation

## Require
- Social Engineering

## ID
cea84b63-1552-47ad-a160-503f1c913390

## References
- [wiki](https://en.wikipedia.org/wiki/Open_redirect)
