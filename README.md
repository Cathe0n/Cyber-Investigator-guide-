# Cyber Investigator guide
This guide aims to assist investigators focused on cybercrime by providing guidance on incident handling, response, and thorough, methodical evidence processing. It is intended as a supplementary resource to support investigators and serve as a reminder, rather than as a standalone procedure.

<div align="center">
    <img src="https://github.com/user-attachments/assets/fdb46b41-594a-4f8e-b736-184b7df58ce4" width="300" height="300">
</div>
Cyber Investigator Experimental Detachment

# Incident handling/response

[![GitHub tag](https://img.shields.io/github/tag/Cathe0n/Cyber-Investigator-guide?include_prereleases=&sort=semver&color=purple)](https://github.com/Cathe0n/Cyber-Investigator-guide/releases/)
[![License](https://img.shields.io/badge/License-Public_Safety_Institution_-purple)](#license)
[![issues - Cyber-Investigator-guide](https://img.shields.io/github/issues/Cathe0n/Cyber-Investigator-guide)](https://github.com/Cathe0n/Cyber-Investigator-guide/issues)


# Table of contents

- [Usage](#usage)


# State of the crime scene.

When processing evidence as an investigator, preserving the crime scene is crucial. Each changes made by a person or you must be documented in order to minimise the chance of evidence tampering. If a client called you to the scene please warn the client to preserve and remove any employees or personnels from the suspected crime scene. An Incident response plan will be necessary in order to properly process a report. (One will be provided soon ^-^ /)

Once you or your team have arrived you must question the client. 

![firefox_YNfIx5wjww](https://github.com/user-attachments/assets/95826c5d-d2f3-4c38-8106-38bc4d27b134)


- What do you think has happened ? 
- What systems are affected ?
- How important is this system to production ?



This can give you an idea/foundation on how to proceed with investigating the incident. Take note of how important the system is to the client, you cannot delay them too much as they are actively losing money. If there’s a time crunch the client should have a backup in place just for such an incident but if that’s not the case try to assist in setting up a backup system (technically not your job though sooo). DO NOT affect the crime scene without documentation. 

You either process the crime scene live and as fast as possible using gKAPE or any other tools (Will be provided in this guide soon!! ^o^), since it’s crucial to the client. This of course limits how many artefacts/crumbs can be gathered compared to the imaging process or also known as offline analysis. 


#Website incident handling (Phishing).

Let’s discuss Websites related incidents, one of the common incidents encountered is defacement of the client’s website. If the clients have set up their webserver properly they must have an SIEM system/IDS in place to deter anything malicious from happening and if that’s the case it’s just about finding the logs and reviewing them and implementing a fix so the incident doesn’t happen again. But it’s not that simple. 

Clients will want a thorough report and investigation done before moving into the eradication process. So this is where we go into the analysis part of the job. Assuming the client has an SIEM/IDS system implemented you must trace what machine or computer committed the malicious activity. Any remote attack MUST originate from an infected system so finding that machine is crucial if it’s a network of machines then ISOLATE them.

Once isolated, perform the identification. If it’s a network of machines it’ll take more than you alone in order to make it quick. In a team, you must command one of your members to interview the employees. While you or another member starts working to isolate the machines from the network. (This is assuming it’s a medium-large company if it’s small then taking it off the grid is needed MAYBE idk what you’re working with ‘ ^ ’)

-What have you done in the past 24hr ?
- Did you notice anything weird when using your computer ? A random CMD popped out of nowhere ? (Say a black window for the elderly >->)
- Downloaded anything recently ?
- Clicked on anything ? 
- Plugged a USB into this machine before ?

With these questions hopefully you can pinpoint WHEN the infection started and WHERE it originated. 

## Email Phishing campaign. 

According to Cloudfare 90% of cyber attacks came from Email Phishing campaigns. So, you shouldn’t be surprised :3.  First analyse the suspect email using EmailDossier or any other tools EML analyzer is awesome too. .This is multiple way to check if the Email address smells fishy (see what I did there :3…No, I won’t stop), just read the results from EML analyzer. and if it doesn’t look official the you know this is where the infection came from…Unless there’s multiple phishing email…So uhh good luck!! ^-^. A phishing Email must have a payload and you can check to see whether it's an executable or a PDF file but these malicious actors are smart and sneaky so they’ll try their best to hide it >.<. Use these tools to help you analyse the payload.

https://analyzer.sublime.security/
https://centralops.net/co/EmailDossier.aspx https://lookup.mxtoolbox.com/dmarc/dmarc-email-tools
### Email analysis.

Alright!!, so you need to navigate through Gmail or whatever this company uses as their main Email provider and find a way to show it’s .eml file. In Gmail it is as shown in the picture. Once you click show original















### Flags

- With `-1` : Lists one entry per line

  ![image](https://user-images.githubusercontent.com/17109060/32149062-4f0547ca-bd25-11e7-98b6-587467379704.png)

- With `-a` (or) `--all` : Does not ignore entries starting with '.'

  ![image](https://user-images.githubusercontent.com/17109060/32149045-182eb39e-bd25-11e7-83d4-897cb14bcff3.png)

- With `-A` (or) `--almost-all` : Does not ignore entries starting with '.', except `./` and `../`

  ![image](https://user-images.githubusercontent.com/17109060/32149046-1ef7664e-bd25-11e7-8bd9-bfc3c8b27b74.png)

- With `-d` (or) `--dirs` : Shows only directories

  ![image](https://user-images.githubusercontent.com/17109060/32149066-5f842aa8-bd25-11e7-9bf0-23313b717182.png)

- With `-f` (or) `--files` : Shows only files

  ![image](https://user-images.githubusercontent.com/17109060/32149065-5a27c9d4-bd25-11e7-9a2b-fd731d76a058.png)

- With `--help` : Prints a very helpful help menu

  ![image](https://user-images.githubusercontent.com/17109060/32149096-cf2cf5b0-bd25-11e7-84b6-909d79099c98.png)

- With `-l` (or) `--long` : Shows in long listing format

  ![image](https://user-images.githubusercontent.com/17109060/32149049-2a63ae48-bd25-11e7-943c-5ceed25bd693.png)

- With `--report` : Shows brief report about number of files and folders shown

  ![image](https://user-images.githubusercontent.com/17109060/32149082-96a83fec-bd25-11e7-9081-7f77e4c90e90.png)

- With `--tree` (or) `--tree=[DEPTH]` : Shows tree view of the directory with the specified depth (default 3)

  ![image](https://user-images.githubusercontent.com/17109060/32149051-32e596e4-bd25-11e7-93a9-5e50c8d2bb19.png)

- With `--gs` (or) `--git-status` : Shows git status for each entry

  ![image](https://user-images.githubusercontent.com/17109060/32149075-7a1a1954-bd25-11e7-964e-1adb173aa2b9.png)

- With `--sd` (or) `--sort-dirs` or `--group-directories-first` : Shows directories first, followed by files

  ![image](https://user-images.githubusercontent.com/17109060/32149068-65117fc0-bd25-11e7-8ada-0b055603e3fd.png)

- With `--sf` (or) `--sort-files` : Shows files first, followed by directories

  ![image](https://user-images.githubusercontent.com/17109060/32149071-6b379de4-bd25-11e7-8764-a0c577e526a1.png)

- With `-t` : Sort by modification time, newest first (NEED TO ADD IMAGE)

- With color options : `--light` or `--dark` can be passed as a flag, to choose the appropriate color scheme. By default, the dark color scheme is chosen. In order to tweak any color, read [Custom configurations](#custom-configurations).

### Combination of flags

- Using `--gs` with `-t` :

  ![image](https://user-images.githubusercontent.com/17109060/32149076-8423c864-bd25-11e7-816e-8642643d2c27.png)

- Using `--gs` with `-l` :

  ![image](https://user-images.githubusercontent.com/17109060/32149078-899b0622-bd25-11e7-9810-d398eaa77e32.png)

- Using `--sd` with `-l` and `-A` :

  ![image](https://user-images.githubusercontent.com/17109060/32149084-9eb2a416-bd25-11e7-8fb7-a9d336c6e038.png)

- Using `--non-human-readable` with `-l` :
  - This will print the file sizes in bytes (non-human readable format)

  ![image](https://user-images.githubusercontent.com/19269206/234581461-1e1fdd90-a362-4cea-ab82-5ca360746be8.png)

# Installation

[(Back to top)](#table-of-contents)

1. Install Ruby (preferably, version >= 2.6)
2. [Download](https://www.nerdfonts.com/font-downloads) and install a Nerd Font. Have a look at the [Nerd Font README](https://github.com/ryanoasis/nerd-fonts/blob/master/readme.md) for installation instructions.

    *Note for `iTerm2` users - Please enable the Nerd Font at iTerm2 > Preferences > Profiles > Text > Non-ASCII font > Hack Regular Nerd Font Complete.*

    *Note for `HyperJS` users - Please add `"Hack Nerd Font"` Font as an option to `fontFamily` in your `~/.hyper.js` file.*

3. Install the [colorls](https://rubygems.org/gems/colorls/) ruby gem with `gem install colorls`

    *Note for `rbenv` users - In case of load error when using `lc`, please try the below patch.*

    ```sh
    rbenv rehash
    rehash
    ```

4. Enable tab completion for flags by entering following line to your shell configuration file (`~/.bashrc` or `~/.zshrc`) :
    ```bash
    source $(dirname $(gem which colorls))/tab_complete.sh
    ```

5. Start using `colorls` :tada:

6. Have a look at [Recommended configurations](#recommended-configurations) and [Custom configurations](#custom-configurations).

# Recommended configurations

[(Back to top)](#table-of-contents)

1. To add some short command (say, `lc`) with some flag options (say, `-l`, `-A`, `--sd`) by default, add this to your shell configuration file (`~/.bashrc`, `~/.zshrc`, etc.) :
    ```sh
    alias lc='colorls -lA --sd'
    ```

2. For changing the icon(s) to other unicode icons of choice (select icons from [here](https://nerdfonts.com/)), change the YAML files in a text editor of your choice (say, `subl`)

    ```sh
    subl $(dirname $(gem which colorls))/yaml
    ```

# Custom configurations

[(Back to top)](#table-of-contents)

You can overwrite the existing icons and colors mapping by copying the yaml files from `$(dirname $(gem which colorls))/yaml` into `~/.config/colorls`, and changing them.

- To overwrite color mapping :

  Please have a look at the [list of supported color names](https://github.com/sickill/rainbow#color-list). You may also use a color hex code as long as it is quoted within the YAML file and prefaced with a `#` symbol.

  Let's say that you're using the dark color scheme and would like to change the color of untracked file (`??`) in the `--git-status` flag to yellow. Copy the defaut `dark_colors.yaml` and change it.

  Check if the `~/.config/colorls` directory exists. If it doesn't exist, create it using the following command:
 
  ```sh
  mkdir -p ~/.config/colorls
  ```

  And then

  ```sh
  cp $(dirname $(gem which colorls))/yaml/dark_colors.yaml ~/.config/colorls/dark_colors.yaml
  ```

  In the `~/.config/colorls/dark_colors.yaml` file, change the color set for `untracked` from `darkorange` to `yellow`, and save the change.

  ```
  untracked: yellow
  ```

  Or, using hex color codes:

  ```
  untracked: '#FFFF00'
  ```

- To overwrite icon mapping :

  Please have a look at the [list of supported icons](https://nerdfonts.com/). Let's say you want to add an icon for swift files. Copy the default `files.yaml` and change it.

  ```sh
  cp $(dirname $(gem which colorls))/yaml/files.yaml ~/.config/colorls/files.yaml`
  ```

  In the `~/.config/colorls/files.yaml` file, add a new icon / change an existing icon, and save the change.


  ```
  swift: "\uF179"
  ```

- User contributed alias configurations :

  - [@rjhilgefort](https://gist.github.com/rjhilgefort/51ea47dd91bcd90cd6d9b3b199188c16)


# Updating

[(Back to top)](#table-of-contents)

Want to update to the latest version of `colorls`?

```sh
gem update colorls
```

# Uninstallation

[(Back to top)](#table-of-contents)

Want to uninstall and revert back to the old style? No issues (sob). Please feel free to open an issue regarding how we can enhance `colorls`.

```sh
gem uninstall colorls
```

# Contributing

[(Back to top)](#table-of-contents)

Your contributions are always welcome! Please have a look at the [contribution guidelines](CONTRIBUTING.md) first. :tada:

# License

[(Back to top)](#table-of-contents)


The MIT License (MIT) 2017 - [Athitya Kumar](https://github.com/athityakumar/). Please have a look at the [LICENSE.md](LICENSE.md) for more details.
