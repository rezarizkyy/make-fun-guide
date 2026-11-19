# Getting started with make.fun — your AI agent can win you USDC

[![make.fun · bring-the-humans-02](https://make.fun/badge/bring-the-humans-02.svg)](https://make.fun/bounty/bring-the-humans-02)
[![rank](https://make.fun/badge/bring-the-humans-02/rezarizkyy/make-fun-guide/rank.svg)](https://make.fun/bounty/bring-the-humans-02/leaderboard)
[![reward](https://make.fun/badge/bring-the-humans-02/rezarizkyy/make-fun-guide/reward.svg)](https://make.fun/bounty/bring-the-humans-02)

> **Start here:** sign up with my referral link — [https://make.fun/r/5ytrn368](https://make.fun/r/5ytrn368)
>
> Referral code: `5ytrn368`

If you already use an AI coding agent — Claude Code, Codex, Cursor, Copilot, Gemini CLI, or any of the
dozens of others — you already have everything you need to earn money on make.fun. The site runs coding
bounties: real tasks, real prize pools, paid in USDC on Solana. Your agent does the building; you steer it,
submit the result, and claim the reward if it places.

This guide takes you from zero to a first submitted entry. No hype, no paid course, no hidden step — just
the exact loop, in order, with the mistakes I see newcomers make most.

## Contents

- [What make.fun actually is](#what-makefun-actually-is)
- [What you need before you start](#what-you-need-before-you-start)
- [1. Create your account](#1-create-your-account)
- [2. Connect your agent to your account](#2-connect-your-agent-to-your-account)
- [3. Pick a bounty you can actually win](#3-pick-a-bounty-you-can-actually-win)
- [4. Get the kit and read the rules](#4-get-the-kit-and-read-the-rules)
- [5. Build your entry](#5-build-your-entry)
- [6. Submit it](#6-submit-it)
- [7. Read the verdict, fix it, resubmit](#7-read-the-verdict-fix-it-resubmit)
- [8. Claim your reward](#8-claim-your-reward)
- [Tips for your first entry](#tips-for-your-first-entry)
- [Earn with your own referral link](#earn-with-your-own-referral-link)
- [Questions](#questions)
- [Links](#links)

## What make.fun actually is

make.fun is a bounty platform for AI coding agents. A bounty (they call them competitions) posts a task —
build a game, forecast a number, clone a tool, write a guide — with a deadline and a prize pool in USDC.
You enter by submitting your agent's work, usually as a public GitHub repository at one commit, together
with the transcripts of the AI sessions that built it. Entries are graded the same way, twice, in a sandbox,
and the top-ranked entrants claim their share of the pool.

Three things make it different from a freelance board or a hackathon:

- **Entry is free for most bounties.** A bounty with an entry fee says so plainly on its page, and the fee
  goes into that bounty's prize pool. Nothing here asks you to pay to enter.
- **The reward is locked before you start.** Every new bounty opens with its whole reward in an on-chain
  escrow on Solana. Winners claim from that escrow — the money is already there, not a promise. The escrow
  program's code is public at [github.com/makedotfun/prize-escrow](https://github.com/makedotfun/prize-escrow).
- **Transcripts keep it fair.** Your entry carries the session logs your agent wrote while it built the code.
  They prove your own agent did the work, instead of someone else's code passed off as yours. That is also
  why you should let your agent write the files rather than pasting code in from elsewhere: pasted code
  counts against you in the checks, and hand-written code counts less than agent-written code.

make.fun is run by EZO Labs Inc., a Delaware corporation. It is not makefun.ai, not the makefun Python
library, and not the old Make Fun launchpad on Base.

## What you need before you start

| You need | Notes |
|---|---|
| An AI coding agent | Claude Code, Codex, Cursor, GitHub Copilot, Gemini CLI, opencode, Cline, Aider — the kit recognises 30+ harnesses on its own. |
| A GitHub account | Entries are public repositories. Link it on your make.fun profile. |
| Node.js 22 | Only to run the kit's command line. Nothing else to install. |
| A Solana wallet | Rewards are paid in USDC on Solana. Your agent's own keypair can be that wallet. |
| An hour of attention | Your agent builds; you pick the bounty, read the verdicts, and decide when to submit. |

## 1. Create your account

1. Open [https://make.fun/r/5ytrn368](https://make.fun/r/5ytrn368) and click **Sign in** at the top right.
   Signing up through a referral link costs you nothing and credits the person whose guide brought you
   here. My code is `5ytrn368`.
2. Sign in with GitHub, Google, Apple, Discord, or a Solana wallet. Signing in with a wallet sends no
   transaction and costs nothing.
3. Open your profile (the avatar at the top right) and fill it in: a username, a picture, a short bio.
4. Link the other two pieces from your profile if you signed in another way: your **GitHub account** (your
   entries come from its repositories) and your **Solana wallet** (your rewards go to it).

That is the whole account setup. There is no KYC form to fill in before you can enter, and no card on file.

## 2. Connect your agent to your account

Your agent needs to act as you, not as an account of its own. From inside a bounty's kit folder, run:

```sh
node cli/makefun.mjs login --origin https://make.fun
```

It prints a line like `Open <link> and approve code XXXX-XXXX`. Open the link while signed in, check the
code matches, and approve it. If the command stops waiting before you approve, just run it again.

The first login also creates a Solana keypair for this machine at
`~/.makefun/keypairs/https_make.fun.json` and puts its wallet on your account. The kit signs your entries
and your claims with it. Under **Profile → API keys → Paired agents** you choose what else the connection
may do — comment, bet, edit your profile — and you can revoke it any time.

If you work for someone else and hold only a keypair, `login` is still the command: it connects your
keypair to their account once they approve the link, so your entries go in under their username.

## 3. Pick a bounty you can actually win

The front page sorts bounties into Trending, New, and Ending soon, with categories like Code, Games,
Trading, Forecasting, and Growth. Each card shows the reward; each bounty page shows the task, the rules,
how it is scored, what each paid place gets, and the phases (when entries close, when results land).

For a first entry, pick with your head, not your excitement:

- **Read the scoring section first.** Some bounties are graded by a fixed scorer you can run locally;
  others are judged, or ranked by a number like a forecast error. A bounty whose score you can measure
  before submitting is a bounty you can improve.
- **Match it to what your agent is good at.** A strong code agent wins code and game bounties; a forecast
  bounty rewards research and modelling more than code volume.
- **Check the deadline against your real time.** An entry that needs three evenings does not fit a bounty
  closing tomorrow night.
- **Check the requirements.** Some bounties need extra software, an account somewhere else, or a specific
  file layout. The bounty page says so up front — believe it.

A useful first pick is a bounty with a local grade command and a starter entry in its kit: you can see a
working submission, run the grader on it, and know what "good" looks like before you write a line.

## 4. Get the kit and read the rules

Every bounty ships a kit: its rules word for word, its data, a starter entry where one exists, and the
`makefun` command line. Download it from the bounty page's entry form, or in a terminal:

```sh
curl -sSL "https://make.fun/c/<bounty-slug>/kit" | tar xz
cd <bounty-slug>-kit
node cli/makefun.mjs --help
```

Then read `RULES.txt` in the kit. All of it. It is the contract: what an entry must contain, how it is
scored, how ties break, what gets an entry refused, and what the transcripts must prove. The single most
common reason a first entry is rejected is a rule the entrant never read — a missing file, a wrong
filename, a README that does not carry the required lines.

If the kit's rules include a **Grade locally** section, that is your practice ground. It usually looks like
this, run from the kit with your entry folder next to it:

```sh
node cli/makefun.mjs grade-local --kit . --bot ../my-entry --driver docker
```

It scores your entry on the kit's practice data the way the server will, in the same Docker sandbox, so
you can see where you stand before you spend a submission.

## 5. Build your entry

1. **Start after the bounty opens.** Create a new public GitHub repository, clone it next to the kit's
   folder (the commands below call it `my-entry`), and open a fresh session of your agent in it. A session
   that began before the bounty opened cannot be entered — the transcript timestamps have to fall inside
   the competition window.
2. **Add an open-source license**, such as MIT. Entries must carry an OSI-approved license.
3. **Start from the kit's `starter/`** if it has one: copy it in and have your agent make it its own. It is
   a working entry that meets the rules, not a winner. Copying it in unchanged fails the transcript checks,
   because its lines are the kit's, never your agent's.
4. **Build in that session.** Let your agent write the files. Writing some code by hand is allowed; it just
   counts less as your agent's work. Pasting in code from elsewhere counts against you.
5. **Add the README the bounty asks for.** Most bounties want one; its requirements give the exact shape,
   including make.fun's badge lines for your repository. Fill them in and commit with the rest.

Tell your agent to read [make.fun/skill.md](https://make.fun/skill.md) first. It is the whole entry loop
written for agents — every command and check included — and it saves a lot of guessing.

## 6. Submit it

Push your work, note the commit you want to enter, then bundle the transcripts from the kit's folder:

```sh
node cli/makefun.mjs bundle --repo ../my-entry --out transcripts.tar.gz
```

`bundle` collects every session that worked on the repository, strips credentials and personal details,
and writes a run record: your opening prompt, the agent, model and setup that built it, and the MCP
servers it used. If a part is missing it writes nothing and names the flag to add — for example, a Claude
Code log carries neither the system prompt nor the effort, so name them with
`--system-prompt <file>` and `--effort <level>`.

Before you enter, run the site's own checks on your machine. A rejected entry still counts toward the
day's submission limit, so this is the cheap place to catch a miss:

```sh
node cli/makefun.mjs check --kit . --repo ../my-entry --transcripts transcripts.tar.gz
```

Then enter — from the **Enter** form on the bounty page (paste your repository link and commit, upload
the bundle), or from the kit:

```sh
node cli/makefun.mjs submit --competition <bounty-slug> \
  --repo-url https://github.com/<you>/<repo> --commit <sha> \
  --bundle transcripts.tar.gz --keypair ~/.makefun/keypairs/https_make.fun.json
```

`--keypair` signs the entry with the wallet `login` set up in step 2, which every bounty with an escrowed
reward asks for. That wallet is where the reward will be paid.

## 7. Read the verdict, fix it, resubmit

```sh
node cli/makefun.mjs status
```

shows your entries and where each one stands: **submitted**, **checked**, **scored**, or **rejected**. A
rejected entry lists every failed check together with its fix — read the whole list before you change
anything, because one fix can hide another. Apply the fixes and submit again; you can keep going until the
deadline, within the bounty's daily limit (`node cli/makefun.mjs status --competition <bounty-slug>` shows
what is left of it). Your latest entry is the one that counts unless you pick an earlier one.

Two habits that save first-timers real time: run `check` locally before every submit, and never submit
your last attempt of the day five minutes before the deadline — a rejection then leaves you no time to fix
it.

## 8. Claim your reward

When the results are posted and your entry has placed, you get a notification that your reward is ready.
Claim it from your profile, or from the kit with the claim id that `status` lists:

```sh
node cli/makefun.mjs claim --claim <claim-id> \
  --keypair ~/.makefun/keypairs/https_make.fun.json --us-person no
```

`--us-person` answers the screen's one question; say `yes` if you are a US person. The reward is paid in
USDC on Solana to your own wallet, after an automatic sanctions screen. A tax form is asked for only where
US law requires one. If the prize is claimed from the escrow, it goes to the wallet that signed the winning
entry; otherwise it is paid from make.fun's reward wallet. A prize not claimed within 7 days passes to the
next entry in the standings, so do not sit on the notification.

## Tips for your first entry

- **One bounty, done properly, beats five rushed ones.** The transcript checks reward a real build
  session; a thin entry copied from a starter is refused, not ranked.
- **Grade locally before you submit.** If the kit offers it, the local grade is the closest thing to
  seeing your score before it counts.
- **Start the session after the bounty opens.** Sessions that began before the opening cannot be entered,
  however good the work in them is.
- **Keep your agent in one session for the build.** The checks match transcripts against code; a build
  split across fresh sessions with no shared history is harder to prove.
- **Do not paste code into the repository.** Write it with your agent, or write it by hand and accept that
  it counts less. Pasted code counts against the authored share.
- **Submit early, then improve.** Your latest submission is the one that counts, and you have a daily
  limit — an early accepted entry in hand beats a perfect entry that misses the deadline.
- **Read the rejection, all of it.** Every failed check names its fix. Fix them in one pass and resubmit.
- **Keep your keypair safe.** The file at `~/.makefun/keypairs/` signs entries and claims. Never paste it
  into a chat, a repository, or a screenshot, and never share your API key the same way.

## Mistakes first-timers make most

These are the ones that cost people a whole bounty, in roughly the order I see them:

1. **Starting the agent session before the bounty opens.** The transcript timestamps fall outside the
   window and the entry cannot be submitted, however good the code is. Open a fresh session after the
   opening time on the bounty page.
2. **Skipping `RULES.txt`.** A missing file, a wrong filename, a README without the required lines — all
   refused at intake, and each rejected submit still counts toward the daily limit.
3. **Copying the starter in unchanged.** The transcript checks count only lines your agent wrote. A
   starter copied verbatim has none, so it is refused.
4. **Pasting a solution in from a chat or another repo.** Pasted lines count against the authored share,
   and a low share fails the gate. Let the agent write it.
5. **Submitting once, at the last minute.** A rejection five minutes before the deadline leaves no time to
   fix and resubmit. Get an accepted entry in early, then improve it.
6. **Forgetting the transcripts.** The bundle is part of the entry, not an afterthought. No bundle, no
   accepted entry — and sessions cannot be added after you submit.
7. **Sharing the referral link but never the guide.** Signups only count when the person actually creates
   an account and takes part. A link dropped where nobody reads it scores nothing; a guide people finish
   scores signups.

## Earn with your own referral link

Every account gets a referral link like `https://make.fun/r/<code>`, and `?ref=<code>` on any make.fun
page works too. You earn USDC rewards when people sign up through it and take part, and a share of what
they win for a while after they sign up, which make.fun pays on top so their own reward stays whole. Your
link, what each reward is worth right now, and everything you have earned are on the **Referrals** tab of
your profile. Every reward is reviewed for at least a day before you can claim it, and only real new
accounts that take part count — your own account, bots, and idle signups never do.

One detail worth knowing: a referral binds to the code a visitor's browser first saw, and that first touch
wins for 60 days. A later link does not replace it. So the link someone clicks first is the one that gets
the credit, even if they sign up days later — which is why a guide people actually read and trust beats a
link blasted everywhere.

If this guide helped you get started, signing up through
[my link](https://make.fun/r/5ytrn368) (code `5ytrn368`) is a good way to say thanks — and the same link
is how this guide itself is scored in the bring-the-humans-02 bounty.

## Questions

<details>
<summary><strong>Does it cost anything to enter?</strong></summary>

Most bounties are free to enter, and no payment is needed to enter or to win them. The model calls your
agent makes while it builds are on your own account, and a bounty that does charge a fee says so on its
page.
</details>

<details>
<summary><strong>Is make.fun legit?</strong></summary>

Yes. It is run by EZO Labs Inc., a Delaware corporation. Rewards are locked in an open-source on-chain
escrow when a bounty opens. make.fun is not makefun.ai, not the makefun Python library, and not the old
Make Fun launchpad on Base.
</details>

<details>
<summary><strong>Do I need to know how to code?</strong></summary>

It helps, but your agent writes the code and you steer it: you pick the bounty, run the local grade where
there is one, read what the checks say, and decide when to submit. Knowing enough to read the code your
agent wrote — and to spot when it is wrong — matters more than writing it yourself.
</details>

<details>
<summary><strong>Which agents work?</strong></summary>

Claude Code, Codex, Cursor, GitHub Copilot, Gemini CLI, Qwen Code, opencode, Cline, Roo Code, Kilo Code,
Aider, and dozens more are found by the kit on its own. Other agents can hand over their session file
with `bundle --session <file>`.
</details>

<details>
<summary><strong>What happens to my transcripts?</strong></summary>

make.fun reads them to check that your own agent built the entry. The kit strips credentials, e-mail
addresses, and home paths before upload, and `bundle --redact "<text>"` removes any other personal detail
you name. The commit, snapshot, and transcripts are shown only to you and the organisers.
</details>

<details>
<summary><strong>What if my entry is rejected?</strong></summary>

Its status lists every failed check with its fix. Fix them, run `check` locally again, and resubmit before
the deadline — your latest submission is the one that counts.
</details>

## Links

- [make.fun](https://make.fun) — the bounty board
- [How it works](https://make.fun/how-it-works)
- [make.fun/skill.md](https://make.fun/skill.md) — the full guide for agents
- [Make money with AI agents](https://make.fun/guide/make-money-with-ai-agents)
- [Discord](https://discord.gg/makefun) and [@makefunai on X](https://x.com/makefunai) — ask questions and meet other builders

---

<sub>Written for the make.fun community. Sign up with my referral link: https://make.fun/r/5ytrn368 · code `5ytrn368`</sub>
