- `grep` is the caveman club for text searching
- `fzf` is the ADHD-friendly search box glued onto your terminal
- ## Grep - "find Text in files."
- ## **Basic usage**
  :LOGBOOK:
  CLOCK: [2025-10-02 Thu 21:25:58]
  :END:
	- ```bash
	  grep "nginx" /etc/nginx/nginx.conf # shows lines containing `nginx`
	  ```
	  ### **`-i` - Case-insensitive**
	  
	  ```bash
	  grep -i "server" /etc/nginx/nginx.conf
	  ```
	  
	  3. **`-R` - Recursive through folders**
	  
	  ```bash
	  grep -Ri "PasswordAuthentication" /etc/ssh # → finds where that SSH option hides.
	  ```
	  
	  4. **`-n` - Show line numbers**
	  
	  ```bash
	  grep -n "ExecStart" /etc/systemd/system/*.service
	  ```
	  
	  5. **`-l` - Just filenames** (useful when you only care _where_)
	  
	  ```bash
	  grep -Rl "proxy_pass" /etc/nginx
	  ```
	- ## Combined Cheat Use (your Scratchpad idea)
	- Keep snippets in `~/cheats.d/`, one file per topic (`ssh.txt`, `nginx.txt`, etc.).
	- Then use:
	  
	    ```bash
	    grep -Ri "proxy" ~/cheats.d
	    ```
	  
	    for brute force search, or:
	  
	    ```bash
	    fzf < ~/cheats.d/ssh.txt
	    ```
	  
	    to interactively pick commands from your SSH cheats.
	- For global snippet picking:
	  
	    ```bash
	    cat ~/cheats.d/* | fzf
	    ```
	  
	  ---
	  
	  >[!info]  
	  >This is the "you can get productive in 10 minutes" version. If you survive and want the Jedi edition, you start piping `rg`(ripgrep) into `fzf` and adding previews that show full configs.