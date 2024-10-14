# SWE_2021_41_2024_2_week_6
---
## Week 4 Asignment 
- [Week4_Repository_Link](https://github.com/JeongYounSeo/SWE_2021_41_2024_2_week)
```
def IsHappy(n):
  seen=set()
  while(n!=1 and n not in seen):
    seen.add(n)
    addSum=0
    for digit in str(n):
      addSum+=int(digit)**2
    n=addSum
  return n==1
```
The provided code defines a function IsHappy(n) that determines whether a number n is a "happy number." A happy number is defined as follows: 
1. Starting with any positive integer, replace the number with the sum of the squares of its digits.
2. Repeat the process until the number equals 1 (which will happen for happy numbers) or it loops endlessly in a cycle that does not include 1 (which happens for unhappy numbers).

### Code Breakdown
- #### Function Definition: `def IsHappy(n):`
  This line defines a function named `IsHappy` that takes a single argument n.
- #### Set for Seen Numbers: `seen=set()`
  This initializes an empty set called `seen` to keep track of numbers that have already been processed to avoid infinite loops. 
- #### While Loop: `while(n!=1 and n not in seen):` 
  The loop continues as long as n is not 1 and has not been seen before.
- #### Add Current Number to Seen: `seen.add(n)`
  The current value of n is added to the `seen` set.
- #### Sum of Squares Calculation:
  The code initializes `addSum` to 0 and then calculates the sum of the squares of each digit in 
n:
```
for digit in str(n):
    addSum += int(digit)**2
```  
  - It converts n to a string, iterates over each digit, converts it back to an integer, squares it, and adds it to `addSum`.
- #### Update n: `n = addSum`
  After calculating the sum of squares, n is updated to this new value.
- #### Return Statement: `return n==1`
  After exiting the loop, the function returns `True` if n is 1 (indicating it is a happy number), and `False` otherwise.
### Conclusion
The function effectively checks if a number is happy by using a set to track previously seen sums and iterating through the process of squaring digits and summing them. This prevents infinite loops caused by cycles.

---
## Week 5 Assignment
> ```
> docker exec ubuntu-container cat /etc/os-release
> ```
>### The Result
> PRETTY_NAME="Ubuntu 24.04.1 LTS"\
> NAME="Ubuntu"\
> VERSION_ID=24.04"\
> VERSIO+CODENAME=noble\
> ID=ubuntu\
> ID_LIKE debian\
> HOME_URL="https://www.ubuntu.com/" SUPPORT_URL="https://help.ubuntu.com/" \
> BUG_REPORT_URL="https://bugs.launchpad.net/ubuntu/" \
> PRIVACY POLICY_URL="https://www.ubuntu.com/legal/terms-and-policies/privacy-policy" UBUNTU CODENAME=noble
LOGO-ubuntu-log
> ### Explanation
> This command uses `docker exec` to run a command inside a running Docker container named `ubuntu-container`. The command `cat /etc/os-release` reads and displays the contents of the `/etc/os-release` file, which contains information about the operating system running in the container.
> - #### Output Details:
>   The output indicates that the container is running Ubuntu 24.04.1 LTS (Noble Numbat), with a specific version and codename.

> ```
> docker exec ubuntu-container git --version
> ```
>### The Result
> git version 2.43.0
>### Explanation
> This command checks the installed version of Git inside the `ubuntu-container`. It again uses `docker exec` to execute the `git --version` command.
> - #### Output Details:
>   The output shows that Git version 2.43.0 is installed in the container.


> ```
> docker exec ubuntu-container Python3 --version
> ```
>### The Result
> Python 3.12.3
>### Explanation
> Similar to the previous commands, this one checks the version of Python 3 installed in the `ubuntu-container` using docker exec.
> - #### Output Details:
>   The output indicates that Python 3.12.3 is installed.

> ```
> docker inspect --format="{{ .HostConfig.Binds }}" ubuntu-container
> ```
>### The Result
> [C:\Users\JYOUNSEO\Documents\python_practice:/app]
>### Explanation
> This command retrieves information about the volume bindings of the `ubuntu-container`. The `docker inspect` command provides detailed information about a container, and the `--format` flag specifies that you want to extract only the bindings information.
> - #### Output Details:
>   The output shows that a directory on the host machine (`C:\Users\JYOUNSEO\Documents\python_practice`) is bound to `/app` in the container. This means any files created or modified in the `/app` directory within the container will reflect in the specified directory on the host.
