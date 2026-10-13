# Lab 7 - Git Exercises
Course: CEP146NDD - Prashanthi Seelam 118738269

GitHub Links:
- Portfolio: https://github.com/vp6wgjc29d-hub/my-portfolio
- Recipe: https://github.com/vp6wgjc29d-hub/recipe-bug-hunt

### Exercise 1: Why did conflict occur?
Both branches desktop-updates (c03b4a3) and master (9c8c053) from same base 65ddd9b edited same lines in portfolio.md Skills section.

### What lines changed?
## Skills section - Desktop had C++, JavaScript, Git:Advanced, Database:SQL - Laptop had Python, Java, Git:Intermediate, Web Dev HTML CSS

### What would have prevented?
git pull before editing, git push after commit on each device, smaller frequent commits.

### Real life avoid conflicts?
Always git pull before start, git push right after commit, git fetch + status to check other device.

### Most challenging part?
Manually merging in nano to keep all skills Python, Java, C++, JavaScript, HTML, CSS, SQL without losing data and removing <<<<<<< ======= >>>>>>> markers.

### How Git helped identify?
Git printed CONFLICT (content): Merge conflict in portfolio.md, git status showed both modified, and inserted markers <<<<<<< HEAD ======= >>>>>>> desktop-updates

### Exercise 2: How many times bisect good/bad?
3 times - git bisect bad on Commit7 0bedf0a, good on Commit4 6b9ebe5, then Git auto checked Commit5 abb9ee7 and found first bad commit.

### 100 commits how many checks?
log2(n) - 7 commits = 3 checks, 100 commits = ~7 checks, 1000 commits = ~10 checks. Manual checkout = 100 checks vs bisect 7.

### Bisect vs checkout difference?
Manual checkout is linear O(n) check each commit. Bisect is binary search O(log n) halves search each time, saves time.

### When most useful?
When hundreds of commits and you know current bad and old good, but don't know which commit broke it. Example: website login worked in Jan release but fails in March.

### What info needed to start bisect?
Need 1 good commit hash (6b9ebe5), 1 bad commit hash (0bedf0a), and test way cat cookies.txt check 350F vs 450F. Commands: git bisect start, bad, good, good/bad, reset.
