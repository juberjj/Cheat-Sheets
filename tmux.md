# tmux - terminal multiplexer

## Prefix
All commands in tmux require the prefix shortcut, which by default is **ctrl+b**.
Below the prefix will be represented by <prefix>

## Basics
    tmux ### Start
    exit ### Exit
    tmux kill-server ### Kill tmux server, along with all sessions

## Windows                                                                                                                                                                             
    <prefix> c  ### Create a new window
    <prefix> ,  ### Rename window
    <prefix> p  ### Previous Window
    <prefix> n  ### Next Window
    <prefix> &  ### Kill Window
    <prefix> f  ### find Window
    <prefix> .  ### Move Window - prompted a number
    <prefix> w  ### List Windows

## Sessions                                                                                                                                                                             
    tmux new -s <session-name>    ### new session
    tmux ls (list-sessions)  ### List open sessions    
    <prefix> d ### Detach from session
    tmux attach -t <session-name>  ### Attach to a named session
    tmux kill-session -t <session-name>  ### Kill a named session

## Panes
    <prefix> "    ### Split Horizontal
    <prefix> %    ### Split Vertical    
    <prefix> q    ### Show panel numbers

    <prefix> x (c)   ### Kill current pane
    <prefix> [arrow key]  ### Move around panes 

## Other
    <prefix> : ### Add named command

## Scenario: Create a job running in the background on a tmux session
    ssh into box
    start a session
    start a long running job, for example, htop
    detach from the session 
    quit the ssh session
    reconnect via ssh 
    verify the session is still active
    reattach to session 

## Scenario: Share a session between 2 users
    ** Create 2 different ssh sessions logging in as the same user to the same machine ** 

    tmux new -s <session-name>  ### Create a new Session
    tmux list-sessions  ### List open sessions    
    tmux attach -t <session-name>    ### Join existing session
    <return> <return>   ### Verify that commands execute in both terminal windows



