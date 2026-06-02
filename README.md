# PowerShell

```bash
# Delete .next / node_modules
Remove-Item -Path ".\.next", ".\node_modules" -Recurse -Force


# Scoop Installation
Set-ExecutionPolicy RemoteSigned -Scope CurrentUser
irm get.scoop.sh | iex

# Fuzzy
scoop install fzf

# Stop node
taskkill /F /IM node.exe /T


```



#### PowerShell: $PROFILE


```bash
# Open profile
notepad $PROFILE


oh-my-posh init pwsh --config "$HOME\fish.omp.json" | Invoke-Expression


function front {
    cd C:\Users\<USER>\projects\frontend
}

function back {
    cd C:\Users\<USER>\projects\backend
}

function src {
	. $PROFILE;
    Write-Host "Profile updated." -ForegroundColor Cyan
}

function st { 
    Clear-Host 
    $folder = Split-Path -Leaf $PWD 
    Write-Host $folder -ForegroundColor Cyan 
    "" 
    Write-Host 'git update-index --skip-worktree <PATH>' -ForegroundColor Gray 
    Write-Host 'git update-index --no-skip-worktree <PATH>' -ForegroundColor Gray 
    ""
    $ignored = git ls-files -v | Where-Object { $_ -match '^S' }
    if ($ignored) {
        Write-Host "-- Arquivos em Skip-Worktree --" -ForegroundColor DarkGray
        $ignored | ForEach-Object { Write-Host $_ -ForegroundColor DarkGray }
        ""
    }
    git status 
    "" 
}
```

#### PowerShell: Fish Theme

```bash
# Create file
notepad $hOME\fish.omp.json
```

###### 

[$hOME\fish.omp.json](fish.omp.json)


## arch linux

### Essential
```bash
# qBitTorrent
sudo pacman -S qbittorrent
```

### Jellyfin

```
pamac build jellyfin 

# Iniciar o serviço agora
sudo systemctl start jellyfin

# Habilitar para iniciar junto com o sistema
sudo systemctl enable jellyfin
```

#### Acessar o Painel de Controle

[localhost:8096](http://localhost:8096)









### PostgresSQL
```
# Connection
psql -h localhost -p 5432 -U postgres -d postgres

# list all databases in the server
\l

# query the list of databases
SELECT datname FROM pg_database;
```

