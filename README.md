# How to Help Contributors Contribute

Potential contributors might have some questions about contributing.  Help them help you!

## Question 1 - How Do I Contribute?

Create a CONTRIBUTING file in your top level directory.

Tell people:

 * How can I find things to do?
 * Do you have rules you want me to follow?
   * Talk to me on big stuff
   * Don't break old stuff
 * Encourage non-functional contributions
   * "Todo" tests
   * Bug reports
   * Docs
   * Meta-stuff (dist.ini, idiomatic usage)
   
## Question 2 - What can I do?

Create a TODO file

 * Try to find some low hanging fruit for new contributors
 
## Question 3 - Code of Conduct

This should be self-explanitory.  Let people know you're going to try to treat them nice.

  https://www.contributor-covenant.org/

See also: Dist::Zilla::Plugin::ContributorCovenant - just add to your dist.ini:

~~~~
  [ContributorCovenant]
~~~~

## Other Things #1 - Name Changes

Use a .mailmap file

Sample lines:

 Joelle Maslak <jmaslak@antelope.net> <joelle.maslak@antelope.net>
 Joelle Maslak <jmaslak@antelope.net>
 
For tools that respect .mailmap, this makes joelle.maslak@antelope.net an alias of the
cannonical jmaslak@antelope.net.  It also makes sure that the name used for these
is "Joelle Maslak".  "git shortlog" automatically uses it.

In your ~/.gitconfig:

~~~~
  [mail]
    mailmap = true
~~~~
    
This tells git to use the .mailmap file for "git log".

## Other Things #2 - Contributor Credit

Use Dist::Zilla::Pluggin::Git::Contributors.

In dist.ini:

~~~~
  [Git::Contributors]
  include_authors=1
  order_by=commits
~~~~

Adds them to the x_contributors section in META.json, used by MetaCPAN.
