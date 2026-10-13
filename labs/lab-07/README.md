# Lab 7 - Git Exercises - CEP146-NDD
**Student:** Prashanthi Seelam - 118738269
**Date:** Oct 13, 2026

## GitHub Repos
- Exercise 1 Portfolio: https://github.com/vp6wgjc29d-hub/my-portfolio
- Exercise 2 Recipe Bug Hunt: https://github.com/vp6wgjc29d-hub/recipe-bug-hunt

---

## Exercise 1: Portfolio Conflicts - Q&A

**Q1: Why did the merge conflict occur?**
Both branches `desktop-updates` (c03b4a3) and `laptop-updates` (9c8c053) were created from same base 65ddd9b and edited the same lines in `portfolio.md` under ## Skills section.

**Q2: What lines of code were changed in each branch?**
- Desktop: Added C++, JavaScript, Git: Advanced, Database: SQL
- Laptop: Added Python, Java, Git: Intermediate, Web Development: HTML, CSS

**Q3: What would have prevented the conflict?**
Doing `git pull` before editing, `git push` right after commit, using smaller frequent commits, communicating which files are being edited.

**Q4: How would you avoid conflicts in real life on multiple devices?**
Always `git pull` before starting work, `git push` immediately after commit, use `git fetch` and `git status` to check other device changes.

**Q5: What was the most challenging part of resolving?**
Manually editing in nano to keep ALL skills (Python, Java, C++, JavaScript, HTML, CSS, SQL) without losing data and correctly removing <<<<<<< HEAD ======= >>>>>>> markers.

**Q6: How did Git help identify and resolve?**
Git printed `CONFLICT (content): Merge conflict in portfolio.md`, `git status` showed both modified, and inserted markers <<<<<<< HEAD ======= >>>>>>> desktop-updates showing both versions.

---

## Exercise 2: Recipe Bug Hunt - Q&A

**Q1: How many times did you have to check the temperature before Git found the bug? Count git bisect good/bad**
3 times - `git bisect bad` on Commit 7 (0bedf0a), `git bisect good` on Commit 4 (6b9ebe5), then Git checked Commit 5 (abb9ee7) which was 450°F BAD. Then Git said `abb9ee7 is the first bad commit`.

**Q2: If you had 100 commits instead of 7, about how many checks would bisect need? Hint log2(n)**
7 commits = log2(7) ≈ 3 checks. 100 commits = ~7 checks, 1000 commits = ~10 checks. Manual checkout would need 100/1000 checks. Bisect saves huge time.

**Q3: How is bisect different from manually checking each commit with git checkout?**
Manual `git checkout` is linear search O(n) - check every commit one by one. `git bisect` is binary search O(log n) - Git picks middle commit and halves search space each time, automated and efficient.

**Q4: When would git bisect be most useful in real projects?**
When large project has hundreds/thousands of commits, current version is broken (bad) and old release worked (good) but you don't know which commit broke it. Example: My recipe worked at Commit 4 (350°F) but broke at Commit 7 (450°F). In real code, website login worked in January but fails in March - bisect finds exact commit.

**Q5: What information do you need to start a bisect session? What do you need to know about good and bad states?**
Need: 1 good commit hash (6b9ebe5 where 350°F good), 1 bad commit hash (0bedf0a where 450°F bad), test method `cat cookies.txt` check temperature, commands `git bisect start`, `bad`, `good`, repeat good/bad, then `git bisect reset`.

---

## Screenshots

### Exercise 1
<img width="1512" height="982" alt="lab 7 1st pic" src="https://github.com/user-attachments/assets/5083097c-792f-43cc-b362-476e379a594c" />


### Exercise 2
<img width="1512" height="982" alt="Screenshot 2026-10-13 at 13 33 49" src="https://github.com/user-attachments/assets/352c7f24-208b-424f-a46d-59c087198aee" />

