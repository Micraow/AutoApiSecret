# AutoApiSecret - Encrypted Edition

# forked from https://github.com/wangziyingwen/AutoApiSecret
AutoAPI Series: AutoAPI, AutoApiSecret, AutoApiSR, AutoAPIS

- Top #
This project is based on the py script of the paran/black man that can correctly call the api on the "assumptions" of the original tutorial (https://blog.432100.xyz/index.php/archives/50/).
This project simply provides an automatic, free, script-free operation without additional equipment, in other words, a machine. (Because the original tutorial required servers/ultra-long-running equipment that most people don't have, this project came into being)
Be sure to read the principle snotation notes and design concepts for understanding the original tutorial (https://blog.432100.xyz/index.php/archives/50/).
:: Carrying the original tutorial (https://blog.432100.xyz/index.php/archives/50/) says: there is no guarantee of renewal! There is no guarantee that it will be renewed! There is no guarantee that we will be able to renew it! Or rather, just increase the likelihood of renewal.
If you understand and accept the above instructions, please proceed; **

Description of the project ###
:: Use github action to implement the time-timed automatic call api, to keep E5 development active.
:: Free, no additional equipment/servers required, deployed without care.
:: Encrypted version, hide the application id plus secret, protect the account security.

Special Notes/Thanks ###
:: Original tutorial blogger-black-screen (Coolend-Paran): https://blog.432100.xyz/index.php/archives/50/
:: General Address: https://github.com/wangziyingwen/AutoAPI
:: Encrypted Address: https://github.com/wangziyingwen/AutoApiSecret
:: Imitation Artificial Application Development (includes upgrade steps): https://github.com/wangziyingwen/AutoApiSR
:: Super Address (Test): https://github.com/wangziyingwen/AutoApiS
:: Update log: https://github.com/wangziyingwen/Autoapi-test
:: Web getrefresh_token gadgets (not recommended): https://github.com/wangziyingwen/GetAutoApiToken
:: Video tutorial: (I'm slow to operate, self-double/fast-forward)
   :: preview online/download address: https://kino-onemanager.herokuapp.com/video/AutoApi%95% 99%99%A8%8B.mp4??
   Station B: https://www.bilibili.com/video/av95688306/
           

The difference ###
   The project uses a public warehouse (open code) and everyone can see your code content.

   So your app id, secret, token will be displayed, not secure.

   Encrypted version, I put the application id, secrets are hidden, tokenbecause of the need to update in real time, can not hide (I will not!) ), much more secure!
   
   Imitating the artificial application development version, as the name implies.
   
--------------------------------------------------------------

Steps ###
The first step is to get a quick look at the original tutorial (https://blog.432100.xyz/index.php/archives/50//) to learn how to get the app id, secret, refresh_token 3 things to facilitate the next step.

The second step, log in/create a new github account, go back to this project page, click on the code for the fork project in the upper right corner to your own account, and then you will have a identical project under your account, the next action is under your project.

  ! (image) (https://github.com/wangziyingwen/ImageHosting/blob/master/AutoApi/fork.png)
  
:: Get app id, secret, refresh_token (copy and save yourself, pay attention to distinguishing id secrets, don't mix) according to the original tutorial (https://blog.432100.xyz/index.php/archives/50/)
   
  Then edit 1.txt in your project online and paste the entire refresh_token overlay (it's my data, delete or overwrite it first). (Don't change 1.py)
  
    The refresh_token position is shown below. Copy the contents of the double quotes immediately following the refresh_token (red vertical box), do not copy the double quotes into it. After copying into 1.txt, be careful not to leave spaces or empty lines at the end
     
    ! (image) (https://github.com/wangziyingwen/Imagehosting/blob/master/AutoApi/tokenlocal.png)
  
In the third step, click on the upper column Settings and Secrets and Add a new secret to create two new secrets: CONFIG_ID, CONFIG_KEY.

  The content is as follows: ( (change your app id to your app id, your app secret change to your secret, single quote do not move)
  
  CONFIG_ID
  ''Shell'
  id'r's your app id'
  ```
  CONFIG_KEY
  ''Shell'
  'Your App Confidential'
  ```
  ! (image) (https://github.com/wangziyingwen/Imagehosting/blob/master/AutoAPI/confidential.png)
  
  The final format should look something like this:
  
  ! (image) (https://github.com/wangziyingwen/Imagehosting/blob/master/AutoAPI/format.png)
  
:: Step 4, go to your personal settings page (top right picture settings, not Settings in the warehouse), select Developer Settings , Personal Access tokens and Generate new tokens,

  ! (image) (https://github.com/wangziyingwen/ImageHosting/blob/master/AutoApi/Settings.png)
  ! (image) (https://github.com/wangziyingwen/ImageHosting/blob/master/AutoApi/token.png)

  Set the name to GITHUB_TOKEN, then check the options of repo, admin:repo_hook, workflow, and finally click Generate token.
  
  ! (image) (https://github.com/wangziyingwen/ImageHosting/blob/master/AutoApi/repo.png)
  ! (image) (https://github.com/wangziyingwen/ImageHosting/blob/master/AutoApi/adminrepo.png)
  ! (image) (https://github.com/wangziyingwen/ImageHosting/blob/master/AutoApi/workflow.png)
  
Step 5, click on the top right corner star/star call immediately once, and then click on the action above to see each run log, see the health

(Need to point in the Test API to see if the api is in place and there is no error.) The outside Auto Api ticking only means that the operation is normal, and we need to confirm that 10 API calls were successful, as in the diagram. If a few apiis is missing, either the api permission is not good when you register the app, or you are not logged in to activate onedrive, login activation)

  ! (image) (https://github.com/wangziyingwen/Imagehosting/blob/master/AutoAPI/log.png)

Step 6, if you don't make any mistakes, you'll get it done! ! Look at the following number of timings to modify, do not intend to change it without mind.

  I set it to run automatically every hour, calling 3 rounds at a time (click on the star/star in the upper right corner can also call once), and you modify it yourself (I don't know how many times and how long to stay active):

  :: Timed auto-start modification place: (in the .github/workflow/AutoApiSecret.yml file, self-drive cron timing task format, minimum every 5 minutes)
   
  ! (image) (https://github.com/wangziyingwen/Imagehosting/blob/master/AutoAPI/timed.png)
   
  :: Where the number of rounds is modified: (at the last end of 1.py)   
  ! (image) (https://github.com/wangziyingwen/Imagehosting/blob/master/AutoAPI/times.png)
  
------------------------------------------------------------
The outside story ###
The API call
  You can go to the graph browser yourself and learn to modify what api to call (the most important thing is to call outlook, onedrive)
  https://developer.microsoft.com/zh-CN/graph/graph-explorer/preview

Introduction to GithubAction ###
Virtual environments provided:

· 2-core CPU
· 7 GB RAM
· 14 GB SSD hard drive space

Restrictions on use:
Each warehouse can only support 20 workflow parallels at the same time.
The GitHub API can be called 1000 times per hour.
Each job can be executed for up to 6 hours.
The free version of the user supports up to 20 job concurrent execution, macOS supports a maximum of 5.
The cumulative monthly usage time of private warehouses is 2000 minutes, after which $0.008/min, and public warehouses are unlimited.

(We use the public warehouse here, by reason, you can set the infinite loop call, and then start it once in 6 hours, guaranteed to call 24 hours a day.
