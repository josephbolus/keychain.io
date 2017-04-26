# keychain.io

Bash
----
Upload your default SSH key:

    curl -s ssh.yourdomain.com/<email>/upload | bash

Install your key into authorized_keys:

    curl -s ssh.yourdomain.com/<email>/install | bash

URLS
----
    ssh.yourdomain.com/<email>
    ssh.yourdomain.com/<email>/upload
    ssh.yourdomain.com/<email>/install
    ssh.yourdomain.com/<email>/fingerprint
    ssh.yourdomain.com/<email>/confirm/<token>
    ssh.yourdomain.com/<email>/all
    ssh.yourdomain.com/<email>/all/install
    ssh.yourdomain.com/<email>/<namedkey>
    ssh.yourdomain.com/<email>/<namedkey>/fingerprint
    ssh.yourdomain.com/<email>/<namedkey>/install
    ssh.yourdomain.com/<email>/<namedkey>/upload

Contributing
------------
~~You will need to create a new S3 bucket~~

Either clone this repository or fork and clone, then install dependencies

    git clone git@github.com:josephbolus/keychain.io.git
    pip install -r requirements.txt

Create a .env file, so that foreman will populate the appropriate environment variables when you start the server with `foreman start`

    $ cat .env
    AWS_ACCESS_KEY_ID=abc123
    AWS_SECRET_ACCESS_KEY=abcd12345698AABBCC
    MAILGUN_API_KEY=key-1234567890abcdefg
    MAILGUN_DOMAIN=mail.yourdomain.com
    KEYCHAIN_BUCKET_NAME=something-keychain.io

For heroku you have to set all these environments via:
    
    xargs -a .env heroku config:set
    
Finally, start the application

    foreman start

Credits
-------
Forked from programming demigod Jeff Lindsay a.k.a "progrium"
[https://github.com/progrium/keychain.io](https://github.com/progrium/keychain.io)

Founder of 
[Glider Labs](https://gliderlabs.github.io/projects/ "Glider Labs Homepage")


