# atcoder 
atcoder : `https://atcoder.jp/home`


また，atcoderの勉強に役に立ちそうな以下の2つのサイトを記しておく．
```
https://kenkoooo.com/atcoder
https://qiita.com/e869120/items/eb50fdaece12be418faa
```  
<br>

VSCode環境構築 参照`https://qiita.com/OcoToOo/items/f1d0a125327f5659ad52`  
VSCodeでデバッグ環境を構築するにはlaunch.jsonのmiDebuggerPathを変更してください．(MinGW-64は以下のサイトを参考にインストールしてください．)  
`https://qiita.com/yamazaki3104/items/91cabd58980c6c17754e`  
(もしかしたらシステム環境変数のpathに以下を追加しなかんかも?
`C:\Program Files\mingw-w64\x86_64-8.1.0-win32-seh-rt_v6-rev0\mingw64\bin`)

SSHでgit cloneしたい場合は ~/.ssh/にrsa_github　とかの暗号かぎ公開鍵を設定してね.
参考: `https://qiita.com/coffee_g9/items/e1b9ab28cfa54f854308`

そのあと， ~/.bashrcに以下の文章をコピペしてね
参考: `https://himadatanode.hatenablog.com/entry/20160823/p14`
```#ssh-agent
SSH_AGENT_FILE=$HOME/.ssh-agent
test -f $SSH_AGENT_FILE && source $SSH_AGENT_FILE
if ! ssh-add -l > /dev/null 2>&1; then
    ssh-agent > $SSH_AGENT_FILE
    source $SSH_AGENT_FILE
    ssh-add $HOME/.ssh/id_rsa
fi
```
それしないと，pushするときとかに，以下のエラーがでて，
それを解決するために毎回以下のコマンドを打たないとダメ.
```
git@github.com: Permission denied (publickey).
fatal: Could not read from remote repository.

Please make sure you have the correct access rights
and the repository exists.
```
`ssh-agent bash`  
`ssh-add ~/.ssh/rsa_github`  
`ssh-add -l`  

