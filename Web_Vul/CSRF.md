[OWASP: CSRF](https://owasp.org/www-community/attacks/csrf)

# Cross-Site request Forgery
CSRF (Cross-Site Request Forgery) is a sneaky attack that tricks your browser into executing actions on a web application without your consent—like changing account settings or sending money—just by clicking on a link. This can lead to serious issues, especially if the target is a website administrator. To defend against CSRF attacks, web applications should implement anti-CSRF tokens to validate requests and use security headers like SOP and CORS to prevent unauthorized cross-origin requests.

## How to Locate Potentially Vulnerable Code
### What’s Happening?
When you interact with a website, like clicking on a link or submitting a form, the website needs to make sure that the request (like transferring money or changing settings) is really coming from you and not from someone trying to trick you.

### Unique Identifiers
To ensure this, websites often add a special code, called a unique identifier or token, to the links or forms you interact with. This code is unique for each user and each action. When you click a link or submit a form, this unique code is sent along with your request. The website checks this code to confirm that the request is really from you.

### Why is This Important?
If a website doesn’t use these unique identifiers, it’s like leaving the door unlocked. Even if you’re logged in (authenticated), a hacker could trick you into clicking a bad link that sends a request to the website pretending to be you. Since the website can’t tell the difference without the unique identifier, it might carry out the action, thinking it’s a legitimate request from you.

### Session ID Isn’t Enough
A Session ID is like a badge that says, "I’m logged in." But this badge is sent with every request you make while you’re logged in, even if you click on a link sent by a hacker. The website only knows that you're logged in, but it doesn’t know if the request is really something you wanted to do. That’s why just having a session ID isn’t enough to protect you.

## Solution:

### Eye for an Eye --> Request for a Request
To protect against CSRF, websites can use a unique code (called a token) that’s added to every action you do. If the code isn’t there or doesn’t match, the website knows something’s wrong and stops the action. Some sites also ask you to enter your password again for important actions, which helps stop hackers who don’t know your password.

Checking if the request has a valid session cookie is not enough, we need to check if a unique identifier is sent with every HTTP request sent to the application. CSRF requests WON’T have this valid unique identifier. The reason CSRF requests won’t have this unique request identifier is the unique ID is rendered as a hidden field on the page and is appended to the HTTP request once a link/button press is selected. The attacker will have no knowledge of this unique ID, as it is random and rendered dynamically per link, per page.

A list is compiled prior to delivering the page to the user. The list contains all valid unique IDs generated for all links on a given page. The unique ID could be derived from a secure random generator such as SecureRandom for J2EE.

1. A unique ID is appended to each link/form on the requested page prior to being displayed to the user.
2. Maintaining a list of unique IDs in the user session, the application checks if the unique ID passed with the HTTP request is valid for a given request.
3. If the unique ID is not present, terminate the user session and display an error to the user.

Implement anti-CSRF tokens, within web applications to validate the authenticity of incoming requests and prevent CSRF attacks by verifying that each request originated from a legitimate source. SOP and CORS headers to restrict cross-origin requests and prevent malicious websites from accessing sensitive data or invoking actions on behalf of authenticated users.

