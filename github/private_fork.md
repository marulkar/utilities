The correct way of creating a private frok by duplicating the repo is documented [here](https://help.github.com/articles/duplicating-a-repository/).

 1. Create a bare clone of the repository.
    (This is temporary and will be removed so just do it wherever.)
    ```bash
    git clone --bare git@github.com:usi-systems/repo.git
    ```

 2. [Create a new private repository on Github](https://help.github.com/articles/creating-a-new-repository/) and name it `repo`.
    > If you are unable to create a private repo, you can request unlimited private repos as a studant by getting
    > the [student pack](https://education.github.com/pack) from Github.

 3. Mirror-push your bare clone to your new `repo` repository.
    > Replace `<your_username>` with your actual Github username in the url below.
    
    ```bash
    cd repo.git
    git push --mirror git@github.com:<your_username>/repo.git
    ```

 4. Remove the temporary local repository you created in step 1.
    ```bash
    cd ..
    rm -rf repo.git
    ```
    
 5. You can now clone your `repo` repository on your machine (in my case in the `code` folder).
    ```bash
    cd ~/code
    git clone git@github.com:<your_username>/repo.git
    ```
   
 6. If you want, add the original repo as remote to fetch (potential) future changes.
    Make sure you also disable push on the remote (as you are not allowed to push to it anyway).
    ```bash
    git remote add upstream git@github.com:usi-systems/repo.git
    git remote set-url --push upstream DISABLE
    ```
    You can list all your remotes with `git remote -v`. You should see:
    ```
    origin	git@github.com:<your_username>/repo.git (fetch)
    origin	git@github.com:<your_username>/repo.git (push)
    upstream	git@github.com:usi-systems/repo.git (fetch)
    upstream	DISABLE (push)
    ```
    > When you push, do so on `origin` with `git push origin`.
   
    > When you want to pull changes from `upstream` you can just fetch the remote and rebase on top of your work.
    ```bash
      git fetch upstream
      git rebase upstream/master
      ```
      And solve the conflicts if any