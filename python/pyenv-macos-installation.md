# Steps to installing latest python (e.g., 3.12.3) on MacOS Sonoma 14.3.1
1. Download the latest python installer from this link: https://www.python.org/downloads/macos/
2. Double click the installer to install the downloaded Python on your MacOS.
3. Open your shell profile file. You can find your shell type by running the following command:
```shell
echo $SHELL
```
I got back:
/bin/zsh

4. As I have Z shell, I will edit my shell profile file below:
```shell
vi ~/.zshrc
```

If your shell is bash, edit the following profile file instead:
```shell
vi ~/.bash_profile
```
(or `vi ~/.bashrc`)

5. At the end of your shell profile file, add the following line:
`export PATH="/Library/Frameworks/Python.framework/Versions/3.12.3/bin:$PATH"`

If you've installed a different Python version, you can find its path from the following path. In that case, update the above PATH value based on your installed Python.
`/Library/Frameworks/Python.framework/Versions/`

Save the file and exit.

6. Apply the change by running this command:
```shell
source ~/.zshrc
```
(or change profile file name to your bash profile file, if using bash.)

7. Now you'll find python3.12.3 on the command prompt:

```shell
python3.12 --version
```
This should return you the following:
Python 3.12.3




