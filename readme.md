# GitlabPushMirror

This is the Gitlab Push Mirror. It is hosted on Gitlab, and **only mirrors all changes happening in the Gitlab repo** on the destination repo (in this case, Github). Whatever **changes made on the Github side will NOT be seen on the Gitlab side**

Source:
https://www.youtube.com/watch?v=ovs-HS0JgqY

---

### GitlabPullMirror

This is possible, but it comes with constraints.

Source: https://docs.gitlab.com/ee/user/project/repository/repository_mirroring.html

---

> **2-Factor Auth** MUST be **disabled** on the Github Repo side

> **Github Repo** MUST be a **Public Repo**

---

### Steps to Creating a Push Mirror Repo on Gitlab

On Gitlab:

1. Import project from destination repo by HTTPS URL
2. Wait for Project to be cloned
3. On the left panel, go to `Settings > Repository > Mirror a repository`
4. Add Git repo URL as `https://<GITHUB_USERNAME>@github.com/<GITHUB_GROUP-NAME> OR <GITHUB_USERNAME>/<PROJECT-NAME>`
5. Specify Mirror Direction as `Push`
6. Add Github Password
   - Be sure to **disable 2-Factor Auth on Github** for this to work
7. Click `Mirror repository`
   - Mirrored Repos will be listed below
   - Wait couple of mins for the process to end<br>
     Page may need to be refreshed until the `Last Successful Update` is shown
8. Click on update button on the list & wait for the status
9. Push new commit on Gitlab repo & check if the change is also seen on the mirroring Github repo

Done: The changes on the Gitlab repo should also be seen on its mirroring repo on Github.
