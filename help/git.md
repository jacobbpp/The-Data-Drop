## Using Git and GitHub

You are encouraged to use Git and a shared GitHub repository for your team’s work.

Why bother with Git for a one day Hackathon?

- It keeps everyone’s work in one place instead of passing files around.
- You get a clear history of changes, so you can roll back if something breaks.
- You can work in parallel without overwriting each other’s code or notebooks.

A simple way to use Git as a team:

- One team member creates a GitHub repo and adds the others as collaborators.
- Create a basic structure, for example:
  - `data/` for the CSV files
  - `notebooks/` or `scripts/` for analysis and cleaning
  - `app/` or `src/` for any app or API code
- Use branches for features. For example:
  - `feature/data-cleaning`
  - `feature/dashboard`
  - `feature/api`
- Make small, frequent commits with clear messages, for example:
  - `Add initial customers and accounts exploration`
  - `Implement join between customers and loans`
  - `Create first version of segment dashboard`
- Merge changes back into `main` only when they run and the team is happy.

Using Git well will:

- Help your team stay organised under time pressure.
- Make it easier to divide work between Software and Data roles.
- Give you something tangible to talk about in your final presentation when you describe how you worked as a team.
