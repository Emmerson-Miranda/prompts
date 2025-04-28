# AI Prompt Documentation

Prompt to create a template of a technical requirement analysis.


## Prompts

**Step 1** - Create a template document

```text
Provide a detailed template in markdown format for creating a formal and technical requirements analysis document for a web application. Ensure the template adheres to industry best practices, organizes sections in a logical sequence, and includes a clear explanation of the purpose and expected content for each section.
```

Output of the previous prompt is captured in [template document](./analysis_template_generated.md).

**Step 2** - Generate the document using the template

```text
I want to create a web application to allow google accounts play tic-tac-toe, so login should be done via google account.

Assist me to create a document based on the template provided, the document output has to be in markdown format. Ask as many question as you need to fill up the the template.
```

After run the previous prompt the expectation is the AI will ask you some questions before start to generate the document, here my replies:

```text
1.
- The goal is only for fun.
- My target audience is any google user in the world, the first stage is European users.
2.
- The functionality is for single player, player vs player will be a future implementation but is out of scope of this document.
- Yes want to provider a game leaderboard across all application users, showing only points, name and country.
3.
- I want to collect name, and country if posssible.
4.
- I want responsive design.
- UI design should be lightweight and compatible with WCAG 2.2 Level A
5.
- Expected 100 concurrent users
- The game will require internet connection.
6.
- Yes future features will be:  player vs random player and challenge another user but both are out of scope.
- Yes application should support multiple languages.
7.
- Backend java, frontend reactjs, database postgresql
- Hosted in AWS
8.
- Updates will be released weekly
- I need CI/CD pipelines aligned with SSDLC
9.
- Any european user can login
- Application will show texts in the user language
- Users can play the game successfully
- Users can see leaderboard and go back to start game page
- For every completed game it will increment its score by 1
10.
- Concersns regardir access and store user data
```

Here is the [analysis document generated based on my responses](./analysis_generated.md).
