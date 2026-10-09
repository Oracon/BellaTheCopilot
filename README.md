# Getting Started — A320 & 737 Copilot Automation

Welcome!

This project is designed to bring a more automated and immersive copilot experience to flight simulation, with support for aircraft such as the Fenix A320 and PMDG 737.

The goal is simple: automate many of the repetitive cockpit tasks that a real-world copilot would normally handle, allowing you to focus more on flying, navigation, ATC, and the overall experience.

Everything provided here is free to use. If you find the project useful and would like to support its development, you can do so through the optional donation/support options available on this page.

## What does this project use?

The automation is built around a few different tools:
- MobiFlight — used to interact with the simulator and control aircraft functions.
- vJoy — provides virtual joystick inputs that can be used by the automation.
- VoiceAttack — handles voice commands and automation. Please note that VoiceAttack is a paid application and must be purchased separately.
- Bella's voice/audio files — provides the voice feedback for the virtual copilot.
- MobiFlight profiles — contain the required simulator controls and automation configuration.
- VoiceAttack profiles — contain the commands and logic used to control the copilot.

You don't need to build the automation yourself. The goal of this project is to provide the configuration, profiles, audio, and instructions needed to get everything working with as little manual configuration as possible.

## Installation Guide

I'll walk you through the entire installation process step by step:

### 1. Install vJoy
Download and install vJoy from the official GitHub repository: [vJoy on GitHub](https://github.com/shauleiz/vJoy)
Once installed, open Configure vJoy and follow these steps:

1. Select vJoy Device: 2.
2. Click Add Device.
3. Change the Number of Buttons to 128.
4. Click Apply.
5. Restart your PC now or at the end of this tutorial.

That's it! vJoy is now configured and ready to be used by the automation.
<img width="367" height="488" alt="image" src="https://github.com/user-attachments/assets/7f96a438-b0e8-41c6-991f-bda1484e6e81" />


Important: The latest version of vJoy may not work correctly with this setup. If you experience issues with vJoy not being detected or the bindings not working, try using an older version of vJoy or the version in the zip file instead.

## 2. Install MobiFlight
Download and install Mobiflight from the official page: https://mobiflight.com/
Once MobiFlight is installed:
1. Go to File → Open.
2. Open the provided 737_PMDG.mfproj profile.
3. Repeat the process and open A320_Fenix.mfproj.
4. Go to Extras → Controller Binding and make sure vJoy is selected.
5. Start the profile by clicking Play, or configure MobiFlight to automatically link the profile to the corresponding aircraft.

### Testing the bindings
If you have more than one vJoy device installed like me, you can test which device is being used directly from MobiFlight.

Open vJoy Feeder and test the assigned buttons/inputs to make sure the bindings are responding correctly.
<img width="1671" height="814" alt="image" src="https://github.com/user-attachments/assets/0c96dd35-15c6-4bcf-875e-a0e98d8dd472" />


## 3. Install VoiceAttack
Install and Configure VoiceAttack 2

VoiceAttack 2 is used to handle the voice commands and automation logic for the virtual copilot.

Note: VoiceAttack is a paid application and must be purchased separately.

### Install VoiceAttack 2
Install VoiceAttack 2 through Steam.

During the installation process, VoiceAttack may redirect you to install the required dependencies. Allow the dependencies to be installed before continuing.

### Windows Speech Recognition

If VoiceAttack shows a message indicating that speech recognition is not configured, you need to enable the appropriate Windows speech components first.

For more information about Windows language packs:

[Microsoft — Language packs for Windows](https://support.microsoft.com/pt-br/windows/hardware/input-devices/language-packs-for-windows)

Windows 11

Open Windows Settings → Time & language → Language & region and make sure the required language and speech components are installed.

Windows 10

Open Settings → Time & Language → Language and make sure the required language and speech components are installed.

### Non-English Windows installations

If your Windows installation is not in English, add English as an additional Windows language and make sure its relevant language/speech resources are installed.

Note: If you cannot add English to Windows, continue with the alternative configuration options provided by VoiceAttack.

Once the language components have been installed successfully, close and reopen VoiceAttack.

### Train the Speech Engine

When VoiceAttack starts again, you may see a prompt asking you to train the speech engine.

Select:
"Let's train the speech engine!"

If you skipped this step, you can start the training manually:

Options (Ctrl + O) → Recognition → Utilities → Speech Engine Training

Complete the training before continuing. This should improve recognition accuracy for the copilot commands.

### Recommended VoiceAttack settings

Open Options (Ctrl + O) and adjust the following settings:

### Recognition

Minimum Confidence Level: 50

Min Unrecognized Confidence Level: 80

### System / Advanced

Run VoiceAttack as Admin: Enabled

Enable vJoy: Enabled ⚠️ IMPORTANT

### Assign vJoy to VoiceAttack

Go to:

General → Joystick Options

Configure:

Joystick 2

Assign 2

Select vJoy

Click OK

After assigning vJoy, restart VoiceAttack.

### Import the profiles

Import the two profiles provided with this project:

Fenix-A320-Profile.vap

PMDG-737-Profile.vap

These profiles contain the commands and automation required for each aircraft.

### Switching between aircraft profiles

There may be situations where VoiceAttack does not correctly switch from one aircraft profile to another.

For example, if you are currently using the 737 profile and want to switch to the A320 profile, simply go to the "Switch Profile" Spoken Command and re-select the A320 profile again.

This forces VoiceAttack to reload the profile after a fresh install. Do the same for A320 profile if you want the Switch Profile command to work both ways.

### Troubleshooting — vJoy DLL version mismatch

If VoiceAttack displays an error such as:

Version of virtual joystick driver does not match dll version: 218 / 219

the vJoy driver and the vJoy DLL used by VoiceAttack are running different versions.

To fix this:
1. Open:
C:\Program Files\vJoy\x86

2. Locate:
vJoyInterface.dll vJoyInterfaceWrap.dll

3. Copy both DLL files.
4. Open your VoiceAttack 2 installation folder, for example:

SteamLibrary\steamapps\common\VoiceAttack 2

5. Replace the corresponding DLL files with the ones from the vJoy installation.
6. Restart VoiceAttack.

After restarting, check that VoiceAttack detects vJoy correctly and that the aircraft profile responds to the configured commands.

Important: If Voice Attack still fails to send vJoy commands, I recommed to double check your version of vJoy or use the one in the zip file.
Verify the integrity of the software files in steam to redownload the original DLL files from Voice Attack.

### VoiceAttack is now ready

At this point, you should have:
- VoiceAttack 2 installed
- Windows speech recognition configured
- Speech engine trained
- vJoy enabled
- vJoy assigned to VoiceAttack
- Fenix A320 profile imported
- PMDG 737 profile imported

The next step is to install Bella's audio files and configure the virtual copilot's voice responses.

## 4. Install Bella's audio files

Copy the Voice Attack Audios folder to the root of your C: drive:

C:\Voice Attack Audios 

Make sure the folder structure and all audio files are preserved.

Once copied, the VoiceAttack profiles will be able to access the required audio files.

### Supported Aircraft

The initial focus of this project is:

✈️ Fenix A320

✈️ PMDG 737

Additional aircraft may be supported in the future depending on interest and the possibilities offered by the simulator and available interfaces.

## Important

This project is an independent community project and is not affiliated with, endorsed by, or sponsored by Fenix Simulations, PMDG, Microsoft, or any of the other software developers mentioned here.

The required third-party applications, such as MobiFlight, vJoy, and VoiceAttack, are maintained by their respective developers.

## What's next?

I'll be publishing individual guide videos covering the procedures of each aircraft and operation of each part of the system.

The objective is to make the setup accessible even if you've never used MobiFlight, vJoy, or VoiceAttack before.

Once everything is installed, you should be able to start a flight, enable the automation, and let your virtual copilot take care of many of the routine cockpit tasks while you concentrate on flying.

Enjoy the flights, and I hope you find the project useful!
✔ [Patreon site](https://www.patreon.com/cw/BrunoTheSimGuy)
