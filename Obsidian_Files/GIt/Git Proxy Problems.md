
# Use config --global http.proxy  to modify proxy 


![[Pasted image 20230929103104.png]]














![[Pasted image 20230929101132.png]]

## When encountering issue like couldn't connect to the server, use this command to save the day

The command you provided, git config --global --unset http.proxy, is used to remove a globally configured HTTP proxy setting in Git. Let me break down what each part of the command does: git config: This is the command to interact with Git's configuration settings. --global: This option specifies that you want to change the global Git configuration, which affects all Git repositories on your user account unless overridden at a local repository level. Global configuration settings are stored in your home directory. --unset: This option is used to unset or remove a configuration setting. In this case, it's used to remove the configuration related to an HTTP proxy. http.proxy: This is the specific configuration key you want to unset. It refers to the HTTP proxy setting in Git. When unset, it removes the HTTP proxy configuration. So, when you run this command, it removes the global HTTP proxy configuration from your Git settings, which means Git will no longer use a proxy for HTTP requests made by Git commands. This can be useful if you want to disable a previously configured proxy or switch to a different proxy configuration.