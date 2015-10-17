---------- Forwarded message ---------

From: Kevin Sawicki (GitHub Staff) <support@github.com>

Date: Wed, Oct 7, 2015 at 8:32 PM

Subject: Re: Software Engineering Project

To: João Mota <redacted>


Hi João,

Thanks for reaching out, here are some details:

> What development process(es) were used and why?

We use pull requests for code review and ping each other for our
specialization areas.  Some team members focus more on core
performance, some on package features, and others on platform issues.

We have continuous integration that does full builds of Atom and runs
our spec suite. We only run tests on Mac but we build Atom on Windows,
Mac, and Linux for every pull request.

We strive to add test coverage for all bug fixes and new features and
pride ourselves on descriptive test names so that we articulate what
the behavior being tested is or what specific regression case it is
covering.

> How is work managed in between the team?

We prioritize inbound issues in our team meeting every Monday.
Anything that gets a special GitHub issue label of `atom` will be
discussed and prioritized. We try and focus on regressions and get
hotfixes out quickly.

Throughout the week we use Slack to communicate. Several members pair
program on features or bug fixes on a weekly basis. We also typically
have a few major projects in flight at a time that different members
of the team are leading.
