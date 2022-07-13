# Documentation:<br ><small>Comment-Based Help</small>

When it comes to sharing pretty much anything designed for PowerShell, probably the most important item on your checklist (besides that pesky "Does it work?" one) has to be the help documentation- __ESPECIALLY__ if said content is intended for any kind of large-scale release (like being published on __[NuGet](https://nuget.org/)__, which is where our modules will go).

One of the features that makes PowerShell such an amazing and easy-to-use shell terminal is the beautifully designed `Get-Help` Cmdlet System. Why is it so amazing? That's a great question, and I will be happy to answer it in the PowerShell Wiki. Sadly, though it might seem like it at times, the `Get-Help` System isn't *actually* magical, and the help documentation doesn't write itself.

## How it Works

Within the `.ps1` or `.psm1` file (key word being *within*), at either the top or bottom (we will be using the *bottom*) of your Function/Module, you will add a *large* `<# Comment Block #>`. This comment block needs to be formatted very specifically in order for the `Get-Help` Cmdlet to be able to read it properly. A full template can be found [here](url), but here's a smaller example with just a Function's __Synopsis__ and __Description__:

<pre>
function Start-MyFunction {
[CmdletBinding()]
  param (
    [Parameter(Mandatory)]
    [string[]]$parameter
    )

  begin {
    # Function Prep
  }
  process {
    # Fancy Function Stuff
  }
  end {
    # Final checks & cleanup
  }

<#
.Synopsys
  This is a function that does cool things.

.Description
  I don't feel like adding more to that, you get the idea.
#>
}
</pre>

The reason I included an entire __Advanced Function Template__ (albeit an extremely basic and condensed one) is because it's __*extremely important*__ that you see *exactly* where the closing __`'#>'`__ tag is placed: __*BEFORE* the closing `'}'` bracket.__

So because I need to be abundantly, __*painfully*__ clear and beat this dead horse:

__For Comment-Based Help to work, the Comment Block must be contained *WITHIN* the Function, than means *inside* the primary bracket container.__

### ✅ Good
<pre>
...and that's why I can't look at salads anymore."
#>
}
</pre>

### ⛔️ Bad
<pre>
...now I'm not allowed in any Fudruckers, nationwide."
}
#>
</pre>

Please feel free to reach out if you have any questions.

Thank you in advance for your contributions in any capacity. ❤️<br >
And as always, happy coding!

<br >
<br >

-----

<br >
<br >

<small>Additional Semi-Relevant Information for those who are interested</small>

## The Alternative

Technically there are two different ways to add documentation for the `Get-Help` Cmdlet to reference, the other being __XML-Based Help__. As the name implies, though, the __XML-Based Help__ method requires the use of *external* `.xml` files, but it also requires:
1. The module be finished *prior* to creating (or at least adding) Help Docs
2. The use of a seperate module, __[PlatyPS](https://docs.microsoft.com/en-us/powershell/utility-modules/platyps/create-help-using-platyps?view=ps-modules)__<br ><small>(unless, God forbid, you try doing it manually)</small>

Now put those two together and think about the nightmare of an update process, whereas updating __*Comment-Based* Help__ can be done alongside any other updates *because it's all in the same place.*


I hope this text turns <span style="">blue</span>