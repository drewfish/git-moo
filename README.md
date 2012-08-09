git-moo
=======

Draws a nice table representing the differences between the local repo and remotes.

It is assumed that there is a direct relationship between the local branch names and remote branch names.



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
                         │ <span class="Cbblue">local</span>  │ drewfish │ isao       │ yahoo     
─────────────────────────┼────────┼──────────┼────────────┼───────────
 0.3.26-pull187          │        │          │            │ b1036f    
 arrow                   │        │          │ 148a6e     │           
 arrowd17c56aa           │        │          │ 83bca1     │           
 build130testfix         │        │          │ fcd6fa     │           
 client-leak-regression  │        │          │ 4bfd82     │           
 custom-binder           │        │          │            │           
 devDependencies         │        │          │            │           
 <span class="Cbblue">develop</span>                 │ <span class="Cblue">2fcc88</span> │ <span class="Cgrey">2fcc88</span><span class="Cblue">=</span>  │ cf895f <span class="Cred">-20</span> │ 29e030 <span class="Cgreen">+9</span> 
 dom-mojit-warning       │        │          │ 2e9520     │           
 <span class="Cbblue">dom-warnings-jslint</span>     │ <span class="Cblue">45fb24</span> │ <span class="Cgrey">45fb24</span>   │            │           
 error-http-reasonphrase │        │          │            │           
 <span class="Cbblue">handlebars3</span>             │ <span class="Cblue">cad4da</span> │          │            │           
 hb4mu                   │        │          │            │           
 jslint                  │        │          │            │           
 <span class="Cbblue">master</span>                  │ <span class="Cblue">5d1785</span> │ <span class="Cgrey">5d1785</span><span class="Cblue">=</span>  │ <span class="Cgrey">5d1785</span>     │ <span class="Cgrey">5d1785</span>    
 mojit-leak              │        │          │ 2dd731     │           
 mojit-leak-036          │        │          │ a33a62     │ a33a62    
 npm                     │        │          │ 240852     │           
 <span class="Cbblue">pr269-ymodel</span>            │ <span class="Cblue">3eb7a7</span> │ <span class="Cgrey">3eb7a7</span><span class="Cblue">=</span>  │            │           
 pull162b                │        │          │ f384f7     │           
 readmes                 │        │          │ 09a43f     │           
 runtime-server-tunnel   │        │          │            │           
 travis                  │        │          │ 3884a2     │           
 use-npm-mime            │        │          │ 88a068     │           
 usr-mw-develop          │        │          │ 1e5dd9     │           
 <span class="Cbblue">yaf-develop</span>             │ <span class="Cblue">ca2f55</span> │ <span class="Cgrey">ca2f55</span><span class="Cblue">=</span>  │            │           
 yui36x                  │        │          │ 5f3bac     │ 5f3bac    
</pre>
<style>
<!--
.Cgrey { color: #888; }
.Cbblue { color: #00F; font-weight: bold; }
.Cblue { color: #00F; }
.Cred { color: #F00; }
.Cgreen { color: #0F0; }
-->
</style>


## To Do
* marker for current branch
* marker if current branch is modified
* use colors from `git config --get-color`


