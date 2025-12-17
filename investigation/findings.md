Challenge ID: CH1

Target URL: http://127.0.0.1:8001/login

Finding Summary: The authentication endpoint issues an access token when a username is supplied without requiring a password, indicating a broken authentication trust assumption.

Detection Method: Manual code review and runtime validation

Template File: N/A

Challenge ID: CH2

Target URL: http://127.0.0.1:8002/download

Finding Summary: Improper path validation in the download endpoint allows access to files outside the intended base directory due to a flawed string-based containment check.

Detection Method: Manual code review and runtime validation

Template File: N/A

Challenge ID: CH3

Target URL: http://127.0.0.1:8003/api/orders/1

Finding Summary: The API grants access to order data based solely on the presence of an Authorization header without validating the token or enforcing user-level authorization.

Detection Method: Manual code review and runtime validation

Template File: N/A


