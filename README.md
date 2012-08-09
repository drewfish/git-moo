git-moo
=======

Draws a nice table representing the differences between the local repo and remotes.

It is assumed that there is a direct relationship between the local branch names and remote branch names.


## Installation
1. Clone this repositry.
2. Copy or symlink `git-moo` somewhere in your `$PATH`.
3. Start using as `git moo` or `git-moo`!


## Usage
<pre>
USAGE:  git moo {options}
Draws a nice table representing the differences between
the local repo and remotes.

It is assumed that there is a direct relationship between
the local branch names and remote branch names.

OPTIONS
    -h
        show this help message

    --local-only or -l
        only show branches that exist locally

    --skip-lonely-branches or -slb
        don't show branches that exist in only one remote

    --skip-remote {remote} or -sr {remote}
        don't show the specified remote
        option can be given multiple times
</pre>


## Example
This example comes from the [mojito](https://github.com/yahoo/mojito) project and a couple of forks.

<pre>
$ git remote -v
drewfish        git@github.com:drewfish/mojito.git (fetch)
drewfish        git@github.com:drewfish/mojito.git (push)
isao    git@github.com:isao/mojito.git (push)
isao    git@github.com:isao/mojito.git (fetch)
yahoo   git@github.com:yahoo/mojito.git (fetch)
yahoo   git@github.com:yahoo/mojito.git (push)

$ git moo
                         │ local  │ drewfish │ isao       │ yahoo     
─────────────────────────┼────────┼──────────┼────────────┼───────────
 0.3.26-pull187          │        │          │            │ b1036f    
 arrow                   │        │          │ 148a6e     │           
 arrowd17c56aa           │        │          │ 83bca1     │           
 build130testfix         │        │          │ fcd6fa     │           
 client-leak-regression  │        │          │ 4bfd82     │           
 develop                 │ 2fcc88 │ 2fcc88=  │ cf895f -20 │ 29e030 +9 
 dom-mojit-warning       │        │          │ 2e9520     │           
 dom-warnings-jslint     │ 45fb24 │ 45fb24   │            │           
 handlebars3             │ cad4da │          │            │           
 master                  │ 5d1785 │ 5d1785=  │ 5d1785     │ 5d1785    
 mojit-leak              │        │          │ 2dd731     │           
 mojit-leak-036          │        │          │ a33a62     │ a33a62    
 npm                     │        │          │ 240852     │           
 pr269-ymodel            │ 3eb7a7 │ 3eb7a7=  │            │           
 pull162b                │        │          │ f384f7     │           
 readmes                 │        │          │ 09a43f     │           
 travis                  │        │          │ 3884a2     │           
 use-npm-mime            │        │          │ 88a068     │           
 usr-mw-develop          │        │          │ 1e5dd9     │           
 yaf-develop             │ ca2f55 │ ca2f55=  │            │           
 yui36x                  │        │          │ 5f3bac     │ 5f3bac    
</pre>


## To Do
* version numbers for this script (to help users track updates)
* marker for current branch
* marker if current branch is modified
* use colors from `git config --get-color`


