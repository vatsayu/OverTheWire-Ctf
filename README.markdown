# OverTheWire Wargames Writeups & Solutions

Hey there! Welcome to my collection of writeups and solutions for the OverTheWire wargames. If you're here, you're probably diving into the fun, challenging world of cybersecurity wargames like I did. This repo is my attempt to document my journey through the OverTheWire challenges, share what I learned, and maybe help you out along the way.

## What's OverTheWire?

If you're new to this, OverTheWire (OTW) is a set of wargames designed to teach and test your skills in Linux, networking, scripting, and security concepts. The games are hands-on, and you’ll need to SSH into their servers, solve puzzles, and escalate privileges to move forward. It’s a fantastic way to learn by doing, and trust me, it’s super addictive!

## What's in This Repo?

This repo contains my writeups and solutions for various OverTheWire wargames, including Bandit, Leviathan, Narnia, and more. Each wargame has its own folder with:

- **Writeups**: Step-by-step explanations of how I approached and solved each level. I’ve tried to keep these clear and beginner-friendly, with some context on why certain commands or techniques worked.
- **Scripts & Tools**: Any scripts (mostly Bash, Python, or C) I wrote to solve challenges, along with notes on how to use them.
- **Tips & Tricks**: Random nuggets of wisdom I picked up while banging my head against the keyboard (we’ve all been there).

### Folder Structure

```
├── bandit/           # Writeups and scripts for Bandit wargame
├── leviathan/        # Writeups and scripts for Leviathan wargame
├── narnia/           # Writeups and scripts for Narnia wargame
├── misc/             # General tools, scripts, or notes that apply across games
└── README.md         # You're reading it!
```

## How to Use This Repo

- **Beginners**: If you’re new to OTW, start with the Bandit wargame. It’s the most beginner-friendly and teaches you the basics of Linux and SSH. Read through the writeups for guidance, but try to solve the challenges yourself first!
- **Intermediate/Advanced**: Check out the other wargames like Leviathan or Narnia for more complex challenges involving coding, privilege escalation, and debugging. My scripts might save you some time, but I encourage you to tweak them or write your own.
- **Spoiler Warning**: These writeups contain full solutions. If you want to enjoy the thrill of solving the puzzles yourself, avoid peeking at the answers until you’re stuck.

## Getting Started with OverTheWire

1. Head to [OverTheWire’s website](https://overthewire.org) and pick a wargame (Bandit is a great starting point).
2. SSH into the game servers using the credentials provided (e.g., `ssh bandit0@bandit.labs.overthewire.org -p 2220`).
3. Follow the instructions for each level to find the password for the next one.
4. If you get stuck, check my writeups for hints or solutions, but don’t give up too quickly—it feels amazing when it clicks!

## My Approach to Writeups

I’ve tried to make these writeups as human-readable as possible. Here’s what you can expect:

- **Clear Explanations**: I explain *why* something works, not just *what* to do. Expect some Linux basics, command breakdowns, and occasional rants about how long it took me to figure something out.
- **Real Talk**: I’ve included my thought process, including the dead ends and mistakes I made. Learning from failures is half the fun!
- **No Fluff**: I’m not here to waste your time. The solutions are to the point, but I’ve added enough context to help you understand the concepts.

## Tools I Used

Here’s a quick rundown of tools and skills that helped me through the wargames:

- **Linux Commands**: `ls`, `cat`, `grep`, `find`, `strings`, `netcat`, etc.
- **Scripting**: Mostly Bash and Python, with a bit of C for some challenges.
- **Debugging**: `gdb` and `strace` for reverse engineering and figuring out what’s going on.
- **Networking**: Understanding ports, protocols, and basic networking concepts.

If you’re new to any of these, don’t worry! The writeups include explanations, and Google is your friend.

## Contributing

Got a better solution? Found a typo? Want to add your own writeups? Feel free to open a pull request or issue. I’m no expert, and I’d love to learn from the community. Let’s make this repo a great resource for everyone tackling OTW.

## A Quick Note

These challenges are meant to be a learning experience, so please don’t just copy-paste the solutions. Struggle a bit, learn the concepts, and you’ll come out of it with real skills. Also, respect OverTheWire’s rules—don’t share passwords or solutions publicly outside of the intended learning context.

## Contact

If you have questions, want to geek out about CTFs, or need a hint, feel free to reach out via GitHub issues or find me on [insert your preferred platform, e.g., X, Discord, etc.]. Happy hacking, and have fun storming the castle!