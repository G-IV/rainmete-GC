# rainmete-GC
A desktop widget for ring calculations for Golf Clash.

I developed this app to give me a desktop widget I coud use instead of needing an excel sheet.

Note: I haven't spent much time comparing the adjustments from Golf Clash Notebook or other apps.  So I won't guarantee the numbers here against those.  But the adjustments in this tool seem to be working out pretty well for me.

Instructions


 

How to change an account name:
Open the GC_Accounts.ini file. 
1) Search for "[AcctSelect1]" (replace the 1 with 2 or 3 depending on which account you are editing)
2) Change the value following "Text="

How to add another account (where n is the account # and n-1 is the previous number):
1) You'll need to copy 4 sections: (example, copy RightBorder2 & Acct3 sections)
    - [RightBorder<n-1>]
    - [Acct<n>SelectBackground]
    - [AcctSelect<n>]
    - [Acct<n>Selected]
2) Paste those at the bottome of the GC_Accounts.in file
3) Change the numbers in the section headers by adding 1 to them
    - [RightBorder2] changes to [RightBorder3]
    - [Acct3SelectBackground] changes to [Acct4SelectedBackground]
    - [AcctSelect3] changes to [AcctSelect4]
    - [Acct3Selected] changes to [Acct4Selected]
4) Adjust the X positions.  If this is your first time, you may have to play with the X values until the text & border are in a good place.  If you hare having a hard time seeing the placement, make these temp changes:
    - In [Acct<3>SelectBackground], change the 
        <Shape=Rectangle 155, #AccountSelectY#, 39, 20 | Fill Color 175,21,255,1 >
        to
        <Shape=Rectangle 155, #AccountSelectY#, 39, 20 | Fill Color 175,21,255,100 >
    - In [RightBorder<n-1>], change the
        <Hidden=1>
        to
        <Hidden=0>
    You should now see a line under the Account<n>Selected and a somewhat clear rectangle behind the account name in the widget.

How to delete an account:
1) You'll need to select 4 sections: (example, copy RightBorder2 & Acct3 sections)
    - [RightBorder<n-1>]
    - [Acct<n>SelectBackground]
    - [AcctSelect<n>]
    - [Acct<n>Selected]
2) Paste those at the bottome of the GC_Accounts.in file

How to handle clubs:
This is going to be repetitive, but hopefully it won't be too unpleasant.
Open the Account Bags.lua file
1) Search for 'Account = {}'
2) Verify that each of your account names are in the following chunk of code.  Right now, you'll see that my account names are here
