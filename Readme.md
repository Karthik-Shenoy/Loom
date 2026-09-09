# Loom

- Loom is a portable contract package for coding agents. Agents write the code. Contracts stay beside it.
- The name comes from handlooms. A loom does the repetitive work, but the weaver chooses the pattern, checks the tension, and fixes defects before they become part of the cloth. Coding agents are similar. They can produce a lot of code quickly, but they cannot know which trade-offs matter unless an engineer states them. Contracts record those decisions and give the agent something concrete to follow and check.
- Choose the contract layer that fits the problem. A shallow contract is faster, but it carries depth debt. You pay it later when unstated decisions make failures, changes, or extensions expensive.

```text
code/
	functions/<name>.contract.yaml
	modules/<name>.contract.yaml
	subsystems/<name>.contract.yaml
	product/<name>.contract.yaml
.contract-driven-dev/
	skills/
		draft/<layer>/SKILL.md
		verify/
			cpp/<layer>/
			go/<layer>/
	references/
		contract-formats/
			function.contract.yaml
			module.contract.yaml
			subsystem.contract.yaml
			product.contract.yaml
	loader.md
```

- Drafting skills turn intent into contracts. Verification scripts check code against them and run without an agent.
- Higher-level contracts reference lower-level contracts. Copying them would create drift.

### Open Q & A (thinking out loud) ?

- How do we reduce redundancy in contracts and code, duplicate info at each of these places will start causing drift and confusion
    - Versioning the contracts is one way of going about things (every commit to the code in scope should upgrade the contract version, or else we would have to run the verifier at some point where versioning is drifting apart)
- Strictness/Static checks while enforcing contracts ?
    - is it scalable across languages
- UI to make code reviews especially test mapping easy ?

### Versioning and design caveats

-
- Languages? :We are starting out with C++ and Go-lang as our initial starting point
