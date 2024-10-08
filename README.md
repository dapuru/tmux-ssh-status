tmux-ssh-status
===============

This is a fork of obxhdx/tmux-ssh-status to kepp control of the source.
Displays ssh username and hostname in tmux status-right and renames window to hostname.

### Usage

Add `#{ssh_status}` format strings to existing `status-right` (or `status-left`) tmux option. Example:

    # in .tmux.conf
    set -g status-right '#{ssh_status} | %a %h-%d %H:%M '

### Options

By default, this plugin will also rename the window to the hostname of the ssh session. To disable this, add the following:

    # in .tmux.conf
    set -g @ssh_auto_rename_window off

### Installation with [Tmux Plugin Manager](https://github.com/tmux-plugins/tpm) (recommended)

Add plugin to the list of TPM plugins in `.tmux.conf`:

    set -g @plugin 'dapuru/tmux-ssh-status'

Hit `prefix + I` to fetch the plugin and source it.

If format strings are added to `status-right` (or `status-left`), they should now be visible.

### Manual Installation

Clone the repo:

    $ git clone https://github.com/dapuru/tmux-ssh-status ~/clone/path

Add this line to the bottom of `.tmux.conf`:

    run-shell ~/clone/path/ssh_status.tmux

Reload TMUX environment:

    # type this in terminal
    $ tmux source-file ~/.tmux.conf

If format strings are added to `status-right` (or `status-left`), they should now be visible.

### Limitations

The time taken to update the status bar will take into account the `status-interval` tmux option. Therefore, you can expect some delay once you move in/out a window where a given ssh connection is active.

### General tmux resources

https://markmcb.com/cli/tmux-zsh-fzf-ui/
https://github.com/rothgar/awesome-tmux
https://leanpub.com/the-tao-of-tmux
https://qmacro.org/blog/posts/2023/11/13/tmux-plugin-development-with-a-local-repo/

### License

[MIT](LICENSE.md)
