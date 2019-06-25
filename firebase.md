# Firebase
If you're new to Firebase, you'll need to create your account and install some tools first.

# Getting Started
* Create a Firebase account at https://www.firebase.com/signup/
* Install the Firebase tools via npm: 
```
sudo npm install -g firebase-tools
```

# Deploy
Once your account has been created and you've signed in, you're ready to deploy!

* Create a new app at **https://www.firebase.com/account/**
* If you haven't previously signed in to the Firebase tools, update your credentials: 
```
firebase login
```
* Initialize your app, and provide the directory (likely work) where your completed app lives: 
```
firebase init
```
* Finally, deploy the app to Firebase: 
```
firebase deploy
```
* Celebrate. You're done! Your app will be deployed to the domain: https://YOUR-FIREBASE-APP.firebaseapp.com

# References
[1]. [Further reading: Firebase Hosting Guide](https://www.firebase.com/docs/hosting/guide/)
