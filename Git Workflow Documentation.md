# Git Workflow
Is document mein, hum Git ke important steps ko samjhenge jaise ki repository initialize karna, changes ko track karna, branching and switching, branches ko merge karna, remote repository pe push karna aur pull updates lena. Har ek point ko aasan tarike se step by step samjhaya gaya hai, saath hi saath commands ke example diye gaye hain.

## 1. Initialize Repository
Repository initialize karna, project ko Git ke andar track karne ka pehla step hota hai.

Nayi directory banao (agar zarurat ho) aur usme jao:

```
mkdir my_project
cd my_project
```
Isse ek nayi folder my_project banegi aur aap us directory mein chale jaoge.

Git initialize karo current directory mein:
```
git init
```
Ye command ek nayi Git repository shuru kar deti hai. .git naam ka ek hidden folder create hota hai jo Git ke sare data ko store karta hai.

Agar ek existing repository clone karna ho (remote se start karne ke liye):

```
git clone <repository_url>
```
Is command se remote URL se puri repository aapke system mein copy ho jayegi.

## 2. Make and Track Changes
Repository initialize ya clone karne ke baad, aap files create ya modify karte ho aur changes ko track karte ho.

Nayi file banao:
```
touch myfile.txt
```
Is command se ek nayi file myfile.txt banegi.

File ko editor mein khol kar content add karo:

```
code myfile.txt
```
(Ya terminal mein edit karne ke liye vim use kar sakte ho)

File ko staging area mein add karo (changes ko track karne ke liye):

```
git add myfile.txt
```
Agar sabhi files ko ek saath stage karna ho, toh git add . command ka use kar sakte ho.

Changes ko commit karo:

```
git commit -m "Added myfile.txt with initial content"
```
Isse Git ke andar file ka snapshot save ho jata hai jo future mein track ho sakta hai.

## 3. Branching and Switching
Branches alag-alag versions par kaam karne ke liye use hote hain bina main project ko impact kiye.

Nayi branch banao:
```
git branch <new-branch-name>
```
Jaise ki:

git branch feature_branch
Nayi branch par switch karo:
```
git checkout <branch-name>
```
Aap ek hi command mein branch create aur switch bhi kar sakte ho:

```
git checkout -b <branch-name>
```
Is branch par changes karo aur commit karo:

```
git add <filename>
git commit -m "Changes on the feature branch"
```
## 4. Merging Branches
Merge karna ek process hai jisme aap ek branch ke changes doosri branch mein daalte ho, jaise feature_branch ko main branch mein merge karna.

Us branch mein switch karo jisme aap merge karna chahte ho (jaise main ya master):

```
git checkout main
```
Feature branch ko current branch mein merge karo:

```
git merge <branch-name>
```
Jaise ki:
```
git merge feature_branch
```
Agar conflicts aaye (toh aapko manually solve karna hoga):

Conflicted file kholkar conflict resolve karo, phir:
```
git add <filename>
git commit -m "Resolved merge conflict"
```
## 5. Push to Remote
Local commits ko remote repository (jaise GitHub ya GitLab) mein bhejne ke liye push command ka use hota hai.

Remote repository add karo (agar pehle se nahi kiya):

```
git remote add origin <repository_url>
```
Changes ko remote repository pe push karo:

```
git push origin <branch-name>
```
Jaise main branch ko push karne ke liye:

```
git push origin main
```
Pehli baar upstream branch set karna ho:

```
git push --set-upstream origin <branch-name>
```
## 6. Pull Updates
Remote repository se latest changes lene ke liye pull command ka use hota hai.

Remote se latest updates fetch karo:

```
git fetch
```
Updates ko apni current branch mein merge karo:

```
git pull origin <branch-name>
```
Agar aap already correct branch mein ho (jaise main), toh simple:

```
git pull
```
