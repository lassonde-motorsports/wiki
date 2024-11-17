# Git etiquette
Git is a powerful tool for version control, and following standard etiquette ensures we unlock its full value. Since **Lassonde Motorsports** aims to help new members develop skills for motorsport vehicle development, we adhere to industry best practices. Below is an overview of the standards we follow at **Lassonde Motorsports**.
## General
Each repository corresponds to a product:
- Each **PCB** is a new product.
- **Control software** is a product with different revisions (e.g., CAN communication or dashboard interface).
## Review
- No one can push to `master` (or controlled revision branches); all branches must be merged via a **Merge Request (MR)**.
- All code must be reviewed by someone else before merging.
- Ideally, nothing is merged into any branch without an MR.
## Branching Strategy
Each Branch is either a feature, hotfix branch, or a dev branch[^Milu][^cheat]. For features and hotfixes, we use the following:
- `hotfix/[ticket_number?]-[description]`
- `feature/[ticket_number?]-[description]`

Where the question mark denotes this field may not exist for that instance.
### general
- `master`
	- Everything from the different dev branches; it's the kitchen sink.
### dev branches
We use dev branches to split different revisions (or applications) of the product. For example the embedded software would have the following dev branches:
- `dashboard-ui`
	- Code for the visual interface and user interaction.
- `can-communication`
	- Code for communication over the CAN network.
- `data-logging`
	- Code for telemetry and performance data logging.
## Commit Messages
Use descriptive tags such as the following at the start of your commit to make it easily identifiable[^cc]:
- `feat:`
- `fix:`
- `BREAKING CHANGE:`

Have a brief title starting with an imperative[^libscp]:
- **fix** not fixing or fixed
- **make** not made or making

Use the description section to show tests passing and complete details of your changes[^libscp]. Don’t say what you changed—git already shows that—but instead say why you changed it.
- don’t say: changed gitignore to include hex files
	- This is in the diff, you haven't said anything new
- do say: stop tracking build output
	- This explains your reason

## References
[^Milu]: [Basic Etiquette](https://dev.to/milu_franz/git-explained-proper-team-etiquette-1od)

[^cc]: [How to write commit messages](https://www.conventionalcommits.org/en/v1.0.0/)

[^libscp]: [Examples of good commit messages](https://github.com/libcsp/libcsp/blob/develop/doc/git-commit.md)

[^cheat]: [Reasonable Cheatsheet](https://medium.com/@abhay.pixolo/naming-conventions-for-git-branches-a-cheatsheet-8549feca2534)