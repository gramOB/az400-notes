# types
issue tracking, bug reports, quality metrics and activity

# tools
github projects
azure boards: kanban, work items, backlogs, sprints, dashboards etc
azure repos: version control. git and tfvc
  - branch policies
which tool to use: github projects vs azure boards
- github: better for teams already using github. only used for git. integrates with 3rd party tools
- azure boards: more comprehensive project management features. has tfvc too. part of az devops suite. customization options.

# using github projects
- click on create project. has kanban, other basic features. 
- create issues manually or from bug/existing issue. 
- create branch from issue

# work items
- basic
  - bug
  - user story
- scrum
  - pbi
  
# connect az boards - > github
## link
AB#789
## automation
Fix #789
## delivery plans
az boardfs too. uses predecessor/successor link types
# integrating tracking tools
from github. search for azure boards from marketplace
from az, follow wizard from boards.
- in commit message from github you can use AB#987 to fix the az boards item
- also use the link from az boards to github commit url or many other thingws

# delivery plans
visualize the sprints and due dates, etc. kind of like gantt chart.

# bug traceability
- bugs are work items
# quality traceability
use azure test plans
automate
monitor