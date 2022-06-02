# Content Aggregation + Email System (CAPES)

Content Aggregator and Email Sender System is a web application for sending and scheduling mails. 
<details>
    <summary><b>Developer Guide</b></summary>

Below is a step-by-step guide to setup the project in your local development environment. 

### Installation

```
pip install virtualenv

virtualenv venv

Windows:
venv\Scripts\activate

Linux/macOS:
source venv/bin/activate.sh

pip install -r requirements.txt

python manage.py migrate

python manage.py runserver
```

### Using Docker Compose

```
docker-compose up
```

## Creating a Environment keys file

Create a file called `.env`on the root of the project structure i.e. the same folder where `manage.py` file is located.

### Database details

Add the following database details as per your configuration of PostgreSQL database.

```
POSTGRES_USER=postgres
POSTGRES_PASSWORD=password
POSTGRES_DB=name_of_database
POSTGRES_HOST=localhost
```

**NOTE: Use `POSTGRES_HOST=db` if using docker-compose.**

### Generating Secret key

To generate a `SECRET_KEY`, you need to open a Python REPL and enter a few commands.

```
python

import secrets

secrets.token_hex(24)
```

Copy the token without the quotes. Add the following in the `.env` file with the copied token.

```
SECRET_KEY=paste_the_token_here
```

</details>


## User Instructions

Below are the user-level instructions for accessing and utilizing the application for sending emails.

### Simple User Account

We simple take in a few inputs for better accountability and proper delivery of emails. We take in the following inputs from the user:

1. Username
2. Email (Gmail Account)
3. Password
4. Google Apps Password

### Generate GAPPS key for sending emails

To be able to send emails, we need a Google Application Key, it is a simple 15 digit key that is used instead of your master password to authenticate you for sending mails.

The Google Apps Key/Password is on only when you have 2FA (Two Factor Authentication) enabled for your GMail Account. After enabling the 2FA, you can head over to the Security Tab and inside the `Signing into Google` Section, you should see the `App Password` option. 

You can create a `Mail` app for your desired Operating System and generate the password. Copy the password and store it in a secure place, we would need that for registering for a account on the project. 

## User Interface

- Search for a keyword
- View the Latest Articles from the searched term.
- Head towards the Send Mail Section.
- Add the required details
    - Mail Recipients (enter manually or extract from CSV file)
    - Subject
    - Edit/Preview the Mail body
    - Schedule type (once/weekly/monthly)
- Send the mail


https://user-images.githubusercontent.com/40317114/171638797-d5a3fe9e-9714-45af-9a97-d3b63925d783.mp4

<details>
  <summary>Capes Home Page</summary>
  
  ![Home Screen](https://res.cloudinary.com/dgpxbrwoz/image/upload/v1651424595/capes/homepage.png)
</details>

<details>
  <summary>Registration Page</summary>
  
![Register Account](https://res.cloudinary.com/dgpxbrwoz/image/upload/v1651424595/capes/register.png)
</details>

 <details>
  <summary>LoginPage</summary>
  
![Login Page](https://res.cloudinary.com/dgpxbrwoz/image/upload/v1651424595/capes/login.png)
</details>

<details>
  <summary>Search Page</summary>
  
![Search Result Page](https://res.cloudinary.com/dgpxbrwoz/image/upload/v1651424595/capes/searchpage.png)
</details>

<details>
  <summary>Mail Form Page</summary>
  
![Mail Form](https://res.cloudinary.com/dgpxbrwoz/image/upload/v1651424595/capes/mailform.png)
</details>
 
 <details>
  <summary>RSS Feed Link Form Page</summary>
  
![RSS Feed Link Adder](https://res.cloudinary.com/dgpxbrwoz/image/upload/v1651424595/capes/rss_feed_link_adder.png)
</details>
   
 <details>
  <summary>Mail Outbox</summary>
  
![Mail Outbox](https://res.cloudinary.com/dgpxbrwoz/image/upload/v1654170547/capes/mail-outbox.png)
</details>
   
 <details>
  <summary>Mail Index Page</summary>
  
![Mail Index Page](https://res.cloudinary.com/dgpxbrwoz/image/upload/v1654170574/capes/mail-index.png)
</details>
