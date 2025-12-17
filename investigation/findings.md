## FINDING 1

**Title:** Authentication logic allows access without password  
**Flag:** Design Assumption Broken  
**Location:** nuclei-bootcamp/apps/ch1-auth/app.py  
**Trigger Condition:** POST request to /login with username but without password  
**Root Cause:** The authentication flow assumes that the presence of a username is sufficient for partial authentication and issues an access token without validating credentials.  
**Impact:** Unauthorized users can obtain an access token without providing valid authentication credentials, breaking the intended security model.  
**Evidence:** A POST request containing only a username returns a 200 OK response with a token (`internal-access`), demonstrating authentication bypass.
## FINDING 2

**Title:** Insecure path validation allows file access outside base directory  
**Flag:** Design Assumption Broken  
**Location:** nuclei-bootcamp/apps/ch2-file/app.py  
**Trigger Condition:** Supplying a crafted file parameter that resolves to a path outside the base directory but still passes the prefix check  
**Root Cause:** The application relies on a string-based path prefix check (`startswith`) to enforce directory boundaries, assuming it guarantees filesystem containment.  
**Impact:** An attacker can access files outside the intended directory, leading to unintended file disclosure.  
**Evidence:** A request to `/download` with a path such as `../files_evil/secret.txt` successfully returns a file located outside the base directory.
