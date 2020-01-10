# .bash_profile
My .bash_profile

```

# The next line updates PATH for the Google Cloud SDK.
if [ -f '/Users/irianto/Downloads/google-cloud-sdk/path.bash.inc' ]; then . '/Users/irianto/Downloads/google-cloud-sdk/path.bash.inc'; fi

# The next line enables shell command completion for gcloud.
if [ -f '/Users/irianto/Downloads/google-cloud-sdk/completion.bash.inc' ]; then . '/Users/irianto/Downloads/google-cloud-sdk/completion.bash.inc'; fi



alias edit="vim /Users/irianto/.bash_profile" 
alias editonvs="code /Users/irianto/.bash_profile" 


# my custom aliases
alias olimpiade="cd /Users/irianto/Documents/Project/olimpiade.id"


# for vscode
code () { VSCODE_CWD="$PWD" open -n -b "com.microsoft.VSCode" --args $* ;}

runservice () { 
	osascript -e 'tell application "Terminal" to do script "port-forward-kds-mongodb"';
	osascript -e 'tell application "Terminal" to do script "run-docker-redis"';	
}

runmetabase () {
	osascript -e 'tell application "Terminal" to do script "port-forward-sql-proxy"';	
	osascript -e 'tell application "Terminal" to do script "port-forward-kds-mongodb"';	
	osascript -e 'tell application "Terminal" to do script "docker start metabase"';		
	osascript -e '
		tell application "Safari"
			open location "http://localhost:3000"
			activate
		end tell';
}

open-nosql () { open -a 'NoSQLBooster for MongoDB';	}

start-ngrok () {
	/Users/irianto/Documents/Project/ngrok http "$1"
}

alias line="open -a 'Line'"



# docker 
alias run-redis="docker run -p 6379:6379 -d redis"
alias run-mongodb="docker run -d -p 27017:27017 -v mongodb-data:/data/db mongo"
alias run-mysql="docker run --rm --name docker-mysql -v mysql_data:/var/lib/mysql -e MYSQL_ROOT_PASSWORD=user123 -p 3306:3306 -d mysql"

# run postgres
alias run-metabase="docker run -d -p 3000:3000 -v metabase-data:/metabase-data -e "MB_DB_FILE=/metabase-data/metabase.db" --name metabase metabase/metabase"
alias run-portainer="docker run -d -p 8000:8000 -p 9000:9000 -v /var/run/docker.sock:/var/run/docker.sock -v portainer_data:/data portainer/portainer"


# for color in terminal
export PS1="\[\033[36m\]\u\[\033[m\]@\[\033[32m\]\h:\[\033[33;1m\]\w\[\033[m\]\$ "
export CLICOLOR=1
export LSCOLORS=ExFxBxDxCxegedabagacad
alias ls='ls -GFh'export PATH="/usr/local/opt/php@7.2/bin:$PATH"
export PATH="/usr/local/opt/php@7.2/sbin:$PATH"
export PATH="/usr/local/opt/php@7.2/bin:$PATH"
export PATH="/usr/local/opt/php@7.2/sbin:$PATH"

```
