# Creating a new user on Ubuntu Server
When setting up a new Ubuntu linux server, the first thing you should do is create a separate user to administer the machine, instead of using the root account. Additionally, this would allow you to set up accounts for multiple users to have access to the server. Since I always seem to Google the steps necessary to do this, I figured I'd document the couple of commands needed to make this happen.

Side note: if you're not logged on as the root user, you'll need to add `sudo` to the front of your commands to make this work.

To create a user, type:
```
adduser [insert user name here]
```

Type in and confirm a new password for the user.

You'll then be prompted to answer a few questions about the user (Name, location, phone number, etc.) I usually just enter the name and leave the rest of the fields blank, but they could be useful in an enterprise setting.

Now you have a user that can login to the server and run some basic commands. In order to do administrative work, however, the user will need to have sudo access.

To do this, enter the following command:
```
visudo
```

A file will appear with a bunch of information related to sudo users. You'll need to find the line that looks like this:

```
root	ALL=(ALL:ALL) ALL
```

Using the format shown above, use the new user's name in place of root. The result should match the following:
```
root	ALL=(ALL:ALL) ALL
newuser	ALL=(ALL:ALL) ALL
```

Make sure you save your changes. If you type `logout` you'll be signed out as root. Using the new user account we just set up, sign into the server. Anytime you run a command that requires advanced privileges, add `sudo` to the start of it and you'll have full control over the server!
