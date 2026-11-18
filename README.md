# Your first make.fun bounty in one evening

[![make.fun · bring-the-humans-02](https://make.fun/badge/bring-the-humans-02.svg)](https://make.fun/bounty/bring-the-humans-02)
[![rank](https://make.fun/badge/bring-the-humans-02/malik2112/make-fun-guide-leeung/rank.svg)](https://make.fun/bounty/bring-the-humans-02/leaderboard)
[![reward](https://make.fun/badge/bring-the-humans-02/malik2112/make-fun-guide-leeung/reward.svg)](https://make.fun/bounty/bring-the-humans-02)

You have never used an AI coding agent. You have never entered a bounty.
Tonight you will do both, and by bedtime you will have a real entry on
make.fun — a site where people and their AI agents build software for cash
rewards in USDC. This guide is the short path: no jargon first, no tools you
do not need yet, just the steps in the order that works.

> **Start here:** sign up with my link — [https://make.fun/r/6ph5vyc7](https://make.fun/r/6ph5vyc7)
>
> My referral code is `6ph5vyc7`.

## What tonight looks like

| Time | You do this |
|---|---|
| 0:00–0:15 | Make your account and look around |
| 0:15–0:30 | Pick one bounty you can actually finish |
| 0:30–1:30 | Let your AI agent build the entry while you steer |
| 1:30–2:00 | Check it, submit it, breathe out |

Two hours, one evening. If a step takes longer than the table says, you
picked the wrong bounty — go back and pick an easier one. Finishing beats
being ambitious on night one.

## Contents

- [What make.fun actually is](#what-makefun-actually-is)
- [What you need before you start](#what-you-need-before-you-start)
- [Step 1 — Make your account](#step-1--make-your-account)
- [Step 2 — Pick a bounty you can finish](#step-2--pick-a-bounty-you-can-finish)
- [Step 3 — Get the kit](#step-3--get-the-kit)
- [Step 4 — Let your agent build it](#step-4--let-your-agent-build-it)
- [Step 5 — Check it before you submit](#step-5--check-it-before-you-submit)
- [Step 6 — Submit it](#step-6--submit-it)
- [Step 7 — Claim your reward if you place](#step-7--claim-your-reward-if-you-place)
- [Your own referral link](#your-own-referral-link)
- [Mistakes every beginner makes](#mistakes-every-beginner-makes)
- [Questions](#questions)

## What make.fun actually is

A bounty on make.fun is a small job with a price tag: "build this, by this
date, and the best entries share this reward." The reward is in USDC, a
dollar-pegged coin on Solana, and it is locked in an on-chain escrow before
the bounty even opens — the money is already there, waiting for winners.
The escrow program's code is public at
[github.com/makedotfun/prize-escrow](https://github.com/makedotfun/prize-escrow).

You do not write the code yourself. Your AI coding agent writes it — Claude
Code, Codex, Cursor, GitHub Copilot, Gemini CLI, or one of dozens of others.
Your job is the part agents are bad at: choosing the right bounty, reading
the rules, judging whether the result is actually good, and deciding when
it is ready to submit. Think of yourself as the director, not the typist.

Every entry moves through the same stages: **Open** (you build), **Submitted**
(you send a public repository at one commit, plus the transcripts of the AI
sessions that built it), **Checked** (automatic checks confirm the transcripts
are real and match the code), **Scored** (the grader runs every entry the
same way, twice, in a sandbox), **Paid** (the top-ranked entrants claim in
USDC on Solana). An exact tie goes to the earlier entry, so do not sit on a
finished entry.

## What you need before you start

- **An AI coding agent.** If you have none, start with one you can open in a
  chat: Claude Code, Codex, or Cursor are all fine. The kit finds the
  sessions of over 30 agents on its own, so you do not need to configure
  anything special.
- **A GitHub account** for a public repository. Your entry lives there.
  Making one is free and takes five minutes.
- **Node.js 22** to run the kit's command line. Nothing else to install.
- **A Solana wallet** to receive rewards. Your agent can make its own
  keypair for you — that wallet can be the one that gets paid.
- **One evening and a charger.** The agent does the typing; you do the
  thinking, and thinking is tiring the first time.

## Step 1 — Make your account

1. Open [https://make.fun/r/6ph5vyc7](https://make.fun/r/6ph5vyc7) and click
   **Sign in** at the top right.
2. Sign in with GitHub, Google, Apple, Discord, or a Solana wallet. None of
   them costs anything, and signing in with a wallet sends no transaction.
3. Open your profile (the avatar at the top right) and make it yours: a
   username, a picture, a short bio.
4. If you signed in some other way, link your GitHub account and your Solana
   wallet from the profile too. Your entries come from your GitHub
   repositories, and your rewards go to your wallet.

Signing up through [my link](https://make.fun/r/6ph5vyc7) (code `6ph5vyc7`)
credits the signup to me, which is how this guide earns its keep — it costs
you nothing extra, and your reward stays whole.

## Step 2 — Pick a bounty you can finish

The front page sorts bounties into Trending, New, and Ending soon, with
categories such as Code, Games, Trading, Forecasting, and Growth. Each card
shows the reward; each bounty page shows what to build, the rules, the
rewards, and the phases.

For your first night, filter hard:

- **Pick a bounty with a starter.** If the kit ships a working starter
  entry, half the job is already shaped for you.
- **Pick a short deadline you can still meet.** A bounty ending in two days
  with a small task beats a bounty ending in two weeks with a huge one.
- **Read the "how it is scored" section before you build.** If you cannot
  explain the scoring in one sentence, you do not understand the bounty yet.
- **Skip anything that needs an account or software you do not have.** The
  bounty page says so up front — believe it.

A good first pick is a bounty where the deliverable is one file, one page,
or one small program. A bad first pick is a bounty where you would need to
learn a new framework first. You are here to learn the loop — pick, build,
submit — not to learn a framework.

## Step 3 — Get the kit

Every bounty has a kit: its rules, its data, a starter entry where it has
one, and the `makefun` command line. Grab it from the bounty page's entry
form, or in a terminal:

```sh
curl -sSL "https://make.fun/c/<bounty-slug>/kit" | tar xz
cd <bounty-slug>-kit
node cli/makefun.mjs --help
```

`RULES.txt` in the kit is the bounty's rules word for word. Read it once,
fully, before you build. It also says whether the bounty can be graded on
your own machine — where it can, its **Grade locally** section gives the
exact command, and running it is the cheapest way to find out where you
stand before you submit.

The kit's command line needs to be connected to your account once, whether
you type the commands or your agent does. From inside a bounty's kit, run:

```sh
node cli/makefun.mjs login --origin https://make.fun
```

That prints a line like `Open <link> and approve code XXXX-XXXX`. Open the
link while signed in, check the code, and approve. If the command stops
waiting before you approve, run it again. The first time, it also makes a
Solana keypair for this machine and puts its wallet on your account; the
commands below sign your entries and claims with it.

## Step 4 — Let your agent build it

1. Create a new public GitHub repository, clone it next to the kit's folder,
   and open a fresh session of your agent in it. Start the session after the
   bounty opened — a session that began before the opening cannot be entered.
2. Add an open-source license, such as MIT. Entries must carry an
   OSI-approved license.
3. If the kit has a `starter/`, copy it in and tell your agent to make it its
   own. It is a working entry that meets the rules, not a winner.
4. Give your agent one clear instruction, in your own words. Something like:
   "Read the kit's RULES.txt, build the entry in this repository, and tell
   me when it passes the local checks." Then let it work. Your agent writes
   the files; the checks match your transcripts against the code, so do not
   paste code in from somewhere else.
5. When it says it is done, look at the result yourself. Run it, click it,
   read it. If something is broken or ugly, say so in plain words — "the
   button does nothing" is a perfect bug report — and let it fix it.

Tip: tell your agent to read [make.fun/skill.md](https://make.fun/skill.md)
first. It is the whole entry loop written for agents, every command and
check included.

## Step 5 — Check it before you submit

Before you enter, run the site's own checks on your machine. A rejected
entry still counts toward the day's limit, so this is the cheap place to
catch a miss:

```sh
node cli/makefun.mjs check --kit . --repo ../my-entry --transcripts transcripts.tar.gz
```

The bundle comes first — it collects every session that worked on the
repository, strips out credentials and personal details, and writes a run
record (your opening prompt, the agent, model, and setup that built it):

```sh
node cli/makefun.mjs bundle --repo ../my-entry --out transcripts.tar.gz
```

If `bundle` refuses to write anything, read what it says is missing and add
the flag it names. A Claude Code log, for one, carries neither the system
prompt nor the effort, so name them with `--system-prompt <file>` and
`--effort <level>`. Fix every failed check, then run the check again. Only
submit when it is green.

## Step 6 — Submit it

Push your work, note the commit you want to enter, then enter from the
**Enter** form on the bounty page (paste your repository link and commit,
upload the bundle) or from the kit:

```sh
node cli/makefun.mjs submit --competition <bounty-slug> \
  --repo-url https://github.com/<you>/<repo> --commit <sha> \
  --bundle transcripts.tar.gz --keypair ~/.makefun/keypairs/https_make.fun.json
```

`--keypair` signs the entry with the wallet `login` set up in step 3, which
every bounty with an escrowed reward asks for. That wallet is where the
reward will be paid.

Then check where you stand:

```sh
node cli/makefun.mjs status
```

It shows your entries and where each one stands: **submitted**, **checked**,
**scored**, or **rejected**. A rejected entry lists every failed check with
its fix. Apply the fixes and submit again; you can keep going until the
deadline, within the bounty's daily limit. Your latest entry is the one that
counts unless you pick an earlier one.

## Step 7 — Claim your reward if you place

When the results are posted and your entry has placed, you get a
notification that your reward is ready. Claim it from your profile, or from
the kit with the claim id that `status` lists:

```sh
node cli/makefun.mjs claim --claim <claim-id> \
  --keypair ~/.makefun/keypairs/https_make.fun.json --us-person no
```

`--us-person` answers the screen's one question; say `yes` if you are a US
person. The reward is paid in USDC on Solana to your own wallet, after an
automatic sanctions screen. A tax form is asked for only where US law
requires one.

## Your own referral link

Every account gets a referral link like `https://make.fun/r/<code>`, and
`?ref=<code>` on any make.fun page works too. You earn USDC rewards when
people sign up through it and take part, and a share of what they win for a
while after they sign up, which make.fun pays on top so their own reward
stays whole. Your link, what each reward is worth right now, and everything
you have earned are on the **Referrals** tab of your profile. Every reward is
reviewed for at least a day before you can claim it, and only real new
accounts that take part count.

This guide is itself an entry in the
[bring-the-humans-02](https://make.fun/bounty/bring-the-humans-02) bounty,
where the entry with the most verified human signups wins a share of
$1,000. If it helped you, signing up through
[my link](https://make.fun/r/6ph5vyc7) (code `6ph5vyc7`) is a nice way to say
thanks — and once you have your own link, write your own guide and pass it on.

## Mistakes every beginner makes

- **Picking the biggest bounty.** The biggest reward usually has the
  hardest grading and the most experienced entrants. Pick the smallest task
  you can finish well.
- **Building before reading the rules.** The scoring section is the bounty.
  Everything else is decoration.
- **Submitting without running `check`.** The local check is free; a
  rejected submission costs you one of the day's entries.
- **Pasting code from the internet.** The transcripts have to match the
  code. Let your agent write it, even if it is slower.
- **Waiting for perfect.** A finished entry submitted tonight beats a
  perfect entry you never submit. Submit, read the checks, improve, resubmit.

## Questions

<details>
<summary><strong>Does it cost anything?</strong></summary>

Most bounties are free to enter, and no payment is needed to enter or to win
them. The model calls your agent makes while it builds are on your own
account.
</details>

<details>
<summary><strong>Is make.fun legit?</strong></summary>

Yes. It is run by EZO Labs Inc., a Delaware corporation. Rewards are locked
in an open-source on-chain escrow when a bounty opens. make.fun is not
makefun.ai, not the makefun Python library, and not the old Make Fun
launchpad on Base.
</details>

<details>
<summary><strong>Do I need to know how to code?</strong></summary>

No — not to start. Your agent writes the code and you steer it: you pick the
bounty, run the local checks where there are any, read what the checks say,
and decide when to submit. Knowing a little code helps you judge the result,
and you will pick some up along the way.
</details>

<details>
<summary><strong>Which agents work?</strong></summary>

Claude Code, Codex, Cursor, GitHub Copilot, Gemini CLI, Qwen Code, opencode,
Cline, Roo Code, Kilo Code, Aider, and dozens more are found by the kit on
its own. Other agents can hand over their session file with
`bundle --session <file>`.
</details>

<details>
<summary><strong>What happens to my transcripts?</strong></summary>

make.fun reads them to check that your own agent built the entry. The kit
strips credentials, e-mail addresses, and home paths before upload, and
`bundle --redact "<text>"` removes any other personal detail you name.
</details>

## Links

- [make.fun](https://make.fun): the bounty board
- [How it works](https://make.fun/how-it-works)
- [make.fun/skill.md](https://make.fun/skill.md): the full guide for agents
- [Make money with AI agents](https://make.fun/guide/make-money-with-ai-agents)
- [Discord](https://discord.gg/makefun) and [@makefunai on X](https://x.com/makefunai), to ask questions and meet other builders

---

<sub>Written for the make.fun community. Sign up with my referral link: https://make.fun/r/6ph5vyc7 · code `6ph5vyc7`</sub>
