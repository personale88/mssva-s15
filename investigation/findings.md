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

Challenge ID: CH4

Target URL: http://ssrf.challenge.hprcse.com/fetch

Finding Summary: The fetch endpoint is designed to perform server-side requests to user-supplied URLs, introducing a server-side request forgery risk if internal address restrictions are not enforced; the target host was not reachable from the testing environment.

Detection Method: Black-box analysis based on documented challenge scope and endpoint behavior

Template File: N/A


Finding Summary: The API grants access to order data based solely on the presence of an Authorization header without validating the token or enforcing user-level authorization.

Detection Method: Manual code review and runtime validation

Template File: N/A

Challenge ID: CH5

Target URL: Not provided

Finding Summary: Challenge 5 is defined as a remote black-box session management assessment; however, no target endpoint was provided to evaluate session handling behavior.

Detection Method: Black-box analysis based on documented challenge scope

Template File: N/A

Challenge ID: CH6

Target URL: http://127.0.0.1:8006/commit

Finding Summary: The application returns a successful commit response even when required workflow state transitions are skipped, resulting in a silent failure and state desynchronization.

Detection Method: Manual code review and runtime validation

Template File: N/A

Challenge ID: CH7

Target URL: Not provided

Finding Summary: The service relies on implicit trust for access decisions without enforcing explicit authentication or authorization controls, indicating an absence of required security checks.

Detection Method: Black-box analysis based on documented challenge scope and access model

Template File: N/A





