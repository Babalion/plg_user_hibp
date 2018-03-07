User HIBP (Have I Been Pwned)
=========================================================================================

This is a Joomla plugin that aims to improve password security for your site's users by preventing them from using a password that is known to have been compromised.

In order to do this, the plugin makes use of the "Have I Been Pwned" API, operated by noted security researcher Troy Hunt.

HaveIBeenPwned.com contains an archive of user credentials that have been made public after being hacked, and allows anyone to query the database to find out whether their credentials have been compromised.

For the purposes of validating a new password, the API can be used to determine whether the password being entered has already been compromised. If the requested password already exists in the HaveIBeenPwned database, it should be assumed to be insecure, because many hacking attempts will use existing known credentials when attempting to crack new passwords.

In addition, the API also returns the number of times that the specified password exists in the database. This can also be used to establish the security (or lack thereof) of a given password; if it exists many times in the database, then it is clearly a commonly used password, and thus vulnerable to attack even if it successfully passes the conventional complexity tests.



Version History
----------------

* v1.0.0     2018-03-06: Initial release.


Installation
----------------
This is a standard Joomla plugin. Installation is via Joomla's extension manager.


Usage
----------------

After installation, the plugin should be enabled via the Joomla plugin manager.

The plugin has a configuration page, but this only contains a single configurable option:

* Max Compromises: This is an integer value that allows you to specify how many times a password should appear in the HaveIBeenPwned database before we prevent it from being used. The default and ideal setting for this is zero, but you may consider this too strict. The option can be set to any value up to 10, 


Caveats, Limitations, To-dos and Notes
--------------------------------------

* Currently, triggering the plugin during signup will result in the entire form being cleared, so the user will need to re-enter everything, not just the password. This is annoying, but will suffice for a first release.
* In the event that the API is broken or offline, the plugin will fail silently and allow the password to be used.
* The API is generally very quick to respond, but it it is possible that there may be a delay in response, particularly in the scenario where the system gets a timeout from the API request.
* Potential future improvement is to issue warnings for passwords that are compromised, but are permitted via the 'Max Compromises' option. User would be allowed to have their password but would be warned that it may be insecure.

References
----------

Documentation for the HaveIBeenPwned API can be found here: https://haveibeenpwned.com/API/v2

The main HIBP site and further information about it can be found at https://haveibeenpwned.com/

The author of HIBP is Troy Hunt. His personal site can be found here: https://www.troyhunt.com/


License
----------------
As with all Joomla extensions, this plugin is licensed under the GPL, specifically in this case, GPLv3. The full license document should have been included with the source code.

The HaveIBeenPwned API is licensed under the Creative Commons Attribution 4.0 International License.
