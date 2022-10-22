# Ansible Playbook for my MacOS Setup

This playbook installs and configures some of the software I use on my Mac for web and software development. Some things in macOS are slightly difficult to automate, so I still have a few manual installation steps, but at least it's all documented here.


##Initial configuration of a brand new Mac
Before starting, I completed Apple's mandatory macOS setup wizard (creating a local user account, and optionally signing into my iCloud account). Once on the macOS desktop, I do the following (in order):

- Install Ansible [following the guide.](https://docs.ansible.com/ansible/latest/installation_guide/index.html)
- Sign in in App Store (since mas can't sign in automatically)
- Clone mac-dev-playbook to the Mac: git clone git@github.com:matruim/macosSetup.git
- Run the playbook with --skip-tags post.
    - If there are errors, you may need to finish up other tasks like installing 'old-fashioned' apps first (since I try to place Photoshop in the Dock and it can't be installed automatically). Then, run the playbook again ;)
- Start Synchronization tasks:
    - Open Photos and make sure iCloud sync options are correct
    - Open Music, make sure computer is authorized, and set Library sync options
    - Open Dropbox, sign in, and set up sync
    - Open KeePassXC, and configure db ( ~/Dropbox/Apps/Keepass/info.kdbx)
- Install old-fashioned apps:
    - Install InjelliJ
    - Install Bartender
    - Install Figma 
    - Install Elgato Stream Deck

- Manual settings to automate someday:
    - System Preferences:
        -Accessibility > Display > Reduce transparency
    - Dock:
        - Add Downloads, Applications, and Work Shortcuts
- After Dropbox Sync completes: Run the playbook with --tags post to complete setup.

- These things might be automatable, but I do them manually right now:
    - Configure Time Machine backup drive and Time Machine Editor (if needed)