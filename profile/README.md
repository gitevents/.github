## GitEvents - Event Management meets Issue Ops

https://gitevents.org

- 🌈 Open & Inclusive Organization
- :octocat: Manage Events, Talks, Suggestions etc. with GitHub Issues
- 🧑‍💻 GitHub GraphQL backend to feed your own website
- 🤖 Automation with GitHub Actions
- 🙈 No databases, admin management, etc.

### Active Actions/Plugins

- 🌈 [Inclusive Org](https://github.com/gitevents/inclusive-org) - every
  interaction with a repo (comment, reaction, discussion, push, etc.) triggers
  an invite to join the GitHub Organization
- 📆 [GitEvents ICS](https://github.com/gitevents/ics) - create a `.ics` file
  for calendar subscriptions (in Apple/Google/etc. Calendar)
- 🤖 [GitEvents Action](https://github.com/gitevents/action) - manage issues
  (code-of-conduct check, etc.), labels etc.
- 🤖 [GitEvents Propaganda](https://github.com/gitevents/propaganda) - propagate
  / spread event to other platforms and sites

### Chat, Discussion & Support

👩‍💻 [Join on Discord](https://discord.gg/m6cphasp4z)

### How It Works

```mermaid
sequenceDiagram
    actor EM as Event Manager
    actor CO as Co-Organizer / Team
    participant GI as GitHub Issues
    participant GA as GitHub Actions

    EM->>GI: Create a new Issue using the Event Form
    loop
    GI->>GA: Trigger Issue Event
    EM->>GI: Add Talks (reference issues), and further details
    GA->>GA: Check Code of Conduct and other requirements
    GA->>GI: Comment issues
    EM->>GI: Review / Fix
    end
    loop
    GA->>GI: Apply label "Ready for Review"
    end
    CO->>GI: Review Event
    CO->>GI: Apply label "Approved"
    GI->>GA: Trigger Approved Event
    GA->>GA: Run .ics generator for calendar subscriptions
    par Propaganda
    GA->>GA: Create Discord Event
    GA->>GA: Create OpenCollective, Facebook, Meetup etc Event (todo)
    GA->>GA: Tweet (todo)
    end
```
