# PowerShell Module Installation

In every <b>New Spectrum PowerShell Module Package</b> there will include a script that can be used to automatically download, install, and setup whichever module the user wants or needs. To oversimplify a rather complicated script, it will be designed to do the following <i>primary</i> tasks:

1. Prep host machine for installation
2. Download & Install the module package from NuGet
3. Configure Module settings according to personal/enterprise use (or both)
4. Import the module into the user's PowerShell profile

The Setup Script is <b>Moderately User-Interactive</b> in order to make what is considered a relatively simple task for us <b><i>Super Users</i></b>, and make it, more or less, a simple task for <i>(almost)</i> <b><i>Any User</i></b>.

> And because I feel the need to point out the obvious: <br >
> <b>Yes, the Setup Scripts will be delivered/downloaded manually-</b> separate from the actual Modules/Packages<br > (even though they are technically included within them).

## Script Details





