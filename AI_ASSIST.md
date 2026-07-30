# AI Usage Log

Record at least one point where you used an AI coding assistant (ChatGPT, Claude, Cursor, GitHub Copilot, Gemini, etc.) during this assignment.

## Interaction 1

- **Tool used:** ChatGPT
- **Task / Problem:** Resolving an unexpected Git error when switching to the Week 13 dbt branch
- **Prompt sent:**
  > `When I run `git switch --track origin/week-13-ch-4-dbt`, Git stops with the error: `The following untracked working tree files would be overwritten by checkout`. The files are `models/marts/_fct_trips.yml` and `packages.yml`. How can I switch branches without accidentally losing my work?`
- **Output provided by AI:**
  > `The AI explained that Git was protecting untracked local files because files with the same paths already existed in the target branch. It suggested checking whether the files were needed, then either moving them temporarily, adding and committing them, or deleting them before switching branches`
- **What I kept, changed, or rejected, and why:**
  > `I first inspected the conflicting files instead of deleting them immediately. I then removed or moved the local copies that were not needed and switched to the required branch successfully. I kept the safety-first approach because it prevented accidental loss of work`

*(Ensure no personal passwords, Databricks tokens, or unapproved credentials are included in prompts or logged outputs.)*
