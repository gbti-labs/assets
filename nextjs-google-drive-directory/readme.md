# GBTI Membership Asset

[![IMAGE ALT TEXT](http://img.youtube.com/vi/B71tP06CDA4/0.jpg)](http://www.youtube.com/watch?v=B71tP06CDA4 "REACT/NextJS app that turns any Google Drive folder into a custom directory application.")

**NextJs Google Drive Directory** is a private repository provided to members of the [GBTI Community](https://gbti.io). 

# NextJs Google Drive Directory

## INTRODUCTION

This is a NextJS React app that provides users a way to access contents of a Google Drive directory through a single page application.

This novel app eliminates the need for users to search through unrelated Google Drive directories, files, and shared folders, reducing clutter in search results.

The app can be hosted for free on platforms such as [Vercel](https://vercel.com/new) and is secured through a secure Google Simple Sign-on process.

## INSTALLATION

First, download the contents of this repository into your local environment for testing and run the following inside the terminal

```bash
npm install
```

Next, lets create the config.json file that will power the application.

## CONFIGURATION

The `config-example.json` file contains the necessary configuration details to connect to the Google Drive API. To set up the connection, you will need to replace the placeholder values in the JSON file with your own Google Drive API credentials and settings.

At the time this readme is written, `config-example.json` looks something like this:

```
{
    "api" : {
        "api_key" : "GOOGLE API KEY HERE",
        "client_id" : "GOOGLE CLIENT ID HERE",
        "client_secret" : "GOOGLE CLIENT SECRET HERE",
        "redirect_uri" : "http://MYDOMIAN.COM/login",
        "scopes" : "https://www.googleapis.com/auth/drive"
    },
    "directory" : {    
        "team_drive" : "TEAM DRIVE ID HERE",
        "target_folder" : "PARENT FOLDER ID HERE"
    },
    "components" : {
        "HeaderImage" : {
            "homepage_url" : "http://MYDOMAIN.COM",
            "logo_url" : "https://LINKTOLOGO.png",
            "logo_alt" : "MY CUSTOM GOOGLE DRIVE DIRECTORY",
            "logo_width" : "300px",
            "logo_color" : "#5b777d"
        }
    }
}
```

### Setting up the Google Drive API
1. Go to the Google Developers Console at https://console.developers.google.com/
2. Create a new project or select an existing one
3. Go to the API Library, select Google Drive API and enable it for your project
4. Go to the Credentials section, select "Create credentials" and choose "OAuth client ID"
5. Choose "Web application" as the application type and fill out the required information.
6. Note the Client ID and Client Secret values, you will need to replace `"GOOGLE CLIENT ID HERE"` and `"GOOGLE CLIENT SECRET HERE"` in the `config-example.json` file with your own Client ID and Client Secret.
7. Inside the Oauth Client ID edit area, inside the Credntials section of your Google Developer Console, You will need to add your `Authorized JavaScript origins` which for your local testing environment should be `http://localhost:3000` and for your production environment `http://MYDOMAIN.COM` (or the full base URL of your application)
8. Also, inside the Oauth Client ID edit area, setup your `Authorized redirect URIs`.  These need to include full URLs to your apps login page that will look like `http://localhost:3000/login` for your localhost environment and  `http://MYDOMAIN.COM/login` for your production environment.
9. In the `config-example.json` file, leave `"https://www.googleapis.com/auth/drive.metadata.readonly"` as the scope. For more information about scopes, you can find the available scopes at https://developers.google.com/identity/protocols/googlescopes

### Setting up the Google Drive Directory
The `directory` section in the `config-example.json` file requires two values to be set: the ID of the team drive and the ID of the starting folder location.
1. Go to the Google Drive web interface and locate the team drive you want to use.
2. Click on the three dots (...) in the top right corner of the drive and choose "Drive settings".
3. Copy the Drive ID, you will need to replace `"TEAM DRIVE ID HERE"` in the `config-example.json` file with your own team drive ID.
4. Locate the folder you want to use as the starting folder location.
5. Click on the three dots (...) next to the folder and choose "Get link".
6. In the "Link to share" dialog, select "Copy link".
7. Extract the folder ID from the copied link, you will need to replace `"PARENT FOLDER ID HERE"` in the `config-example.json` file with your own folder ID.

### Customizing the Components
The `components` section in the `config-example.json` file contains cosmetic details that can be customized as desired. Replace the values in this section with your desired values.

### Final Step
Once you have replaced all the placeholder values in the `config-example.json` file with your own values, you can remove `-example` from the filename to enable the configuration file.

Once you are done your `config.json` file should look something like this:

```config.json
{
    "api" : {
        "api_key" : "AIzaSyDEsyMKrmCJHb8v_NHyJv_wMDhfgUfgsu",
        "client_id" : "590454986992-o6uaho5dtgtgyhdss7nqccrr6e.apps.googleusercontent.com",
        "client_secret" : "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",
        "redirect_uri" : "http://localhost:3000/login",
        "scopes" : "https://www.googleapis.com/auth/drive"
    },
    "directory" : {    
        "team_drive" : "0AIDUUK1SmUbSPdU7EA",
        "target_folder" : "1ePFd-ssH4ja1-7_x6tNgd-5CT9HbsAIb"
    },
    "components" : {
        "HeaderImage" : {
            "homepage_url" : "http://localhost:3000/",
            "logo_url" : "https://logovtor.com/wp-content/uploads/2021/06/some-logo-vector.png",
            "logo_alt" : "My Logo",
            "logo_width" : "300px",
            "logo_color" : "#5b777d"
        }
    }
}
```

### Launch the dev server

If everything is setup correctly, you should be ready to launch the dev server.

```bash
npm run dev
```

Open [http://localhost:3000](http://localhost:3000) with your browser to see the result.

If all is well you should see your app in motion!

## DEPLOYMENT

The easiest way to deploy your Next.js app is to use the [Vercel Platform](https://vercel.com/new?utm_medium=default-template&filter=next.js&utm_source=create-next-app&utm_campaign=create-next-app-readme) from the creators of Next.js.

Check out our [Next.js deployment documentation](https://nextjs.org/docs/deployment) for more details.

## ABOUT GBTI LABS

Thanks for being a part of the GBTI developer community!

GBTI Labs is a paid membership community that provides exclusive access to an expanding collection of innovative and novel open source assets. Our community is dedicated to promoting collaboration and shared learning through a private Discord network. We encourage members to contribute to the improvement of shared assets and knowledgebases.

## SUPPORT DISCLAIMER

The purchase of access to this and other GBTI Labs private repositories only grants access to the code and communities, not to support services.

That being said, we hope that the community will provide light support services as required. Please refer to the GBTI Discord community where fellow users may be able to assist you with your inquires.

Please be aware that support is not guaranteed and requests for help may take up to 48 hours for a reply.

Depending on the complexity of your request, you may be recommended to a third-party support vendor with hourly rates ranging from 80-120USD.

GBTI Labs does not provide refunds after onboarding. Once a user has access to the code base, they will remain in access during the duration of their subscription.

Per the current subscription model, subscriptions include access to the GBTI community as well as access GBTI private repositories as long as the subscription is active.

# Release Notes

## Feb 4, 2023

The first verson of this asset has been produced.

### Progress
* File search is limited to 2 levels
* Starting directory/folder must be hosted within a shared Team folder.

### Plans
* Write in settings for supporting non team folders
* investigate deep(er) nested searches. 

