
## Prerequisites 

1. Run the [Postgres](http://get.enterprisedb.com/postgresql/postgresql-9.5.1-1-windows-x64.exe) installer.

2. Set the password for `postgres` to be `api`.

3. Using the `pgAdmin` tool, create a database called `eth`.

4. Add `C:\Program Files\PostgreSQL\9.5\bin` `C:\Program Files\PostgreSQL\9.5\lib` to the path.

5. Run `jsonview.reg` if you want to look at JSON in Internet Explorer.

## Installing

1. Unzip `strato.zip`
2. Run `strato-init.ps1`
3. Open a powershell for each process and run
- `strato-adit.ps1`
- `strato-quarry.ps1`
- `ethereum-vm.ps1`
- `strato-api.ps1`

(`strato.ps1` should be able to do this, but I can't get the processes to actually respond in the background).

Look at the [api](http://localhost:3000)

Open a powershell terminal and invoke the faucet:
- `$postParams = @{address='123'}`

- `Invoke-WebRequest -Uri http://localhost:3000/eth/v1.1/faucet -Method POST -Body $postParams`

Open the [stats](http://localhost:3000/stats) and see if the block got processed.

## How and what to build *Strato* on Windows (to be completed)

# Installing `Strato` on windows

pacman -S base-devel git
pacman -S mingw-w64-x86_64-toolchain

Set `resolver=ghc-7.10.3` (you might need to run `stack solver --update-config`) or run `stack install --resolver=ghc-7.10.3` .


### Static libraries

We create a library holding both `leveldb` and `stdc++`

We need `pthread`

### TODO

- Use release version of all dependent libraries
- Check all compiler optimization
- check using `-split-objs`
- use UTX ?