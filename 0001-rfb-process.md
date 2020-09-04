# RFB-1 - RFB Purpose and Guidelines

* RFB: 1
* Title: RFB Purpose and Guidelines
* Author: `Todd Rinaldo <toddr@cpan.org>`
* Status: Active
* Type: Process
* Created: 2020-09-03
* Sponsor: Todd Rinaldo
* Post-History: TBD

## What is a RFB?

RFB stands for Request for Bikeshed. A RFB is a design
document providing information to the Perl community, or describing
a new feature for Perl or its processes or environment.  The RFB
should provide a concise technical specification of the feature and a
rationale for the feature.

We intend RFBs to be the primary mechanisms for proposing major new
features, for collecting community input on an issue, and for
documenting the design decisions that have gone into Perl.  The RFB
author is responsible for building consensus within the community and
documenting dissenting opinions.

Because the RFBs are maintained as text files in a versioned
repository, their revision history is the historical record of the
feature proposal.

Why Bikeshed? This is a joking reference to the [Law of Triviality](https://en.wikipedia.org/wiki/Law_of_triviality).
We also hope this helps us be mindful during development of changes to keep our eyes on the goal!

##  RFB Audience

The typical primary audience for RFBs are the core developers of the Perl
Programming Language.

However, other parts of the Perl community may also choose to use the process
(particularly for Informational RFBs) to document expected API conventions and
to manage complex design coordination problems that require collaboration across
multiple projects.

## RFB Types

There are three kinds of RFB:

1. A **Standards Track** RFB describes a new feature or implementation
   for Perl. It may also describe an interoperability standard that will
   be supported outside the standard library for current Perl versions
   before a subsequent RFB adds standard library support in a future
   version.

2. An **Informational** RFB describes a Perl design issue, or
   provides general guidelines or information to the Perl community,
   but does not propose a new feature.  Informational RFBs do not
   necessarily represent a Perl community consensus or
   recommendation, so users and implementers are free to ignore
   Informational RFBs or follow their advice.

3. A **Process** RFB describes a process surrounding Perl, or
   proposes a change to (or an event in) a process.  Process RFBs are
   like Standards Track RFBs but apply to areas other than the Perl
   language itself.  They may propose an implementation, but not to
   Perl's codebase; they often require community consensus; unlike
   Informational RFBs, they are more than recommendations, and users
   are typically not free to ignore them.  Examples include
   procedures, guidelines, changes to the decision-making process, and
   changes to the tools or environment used in Perl development.
   Any meta-RFB is also considered a Process RFB.

## Definitions

### The Pumpking

There are several references in this RFB to "The Pumpking". This refers to
the current project lead for the language. The Pumpking is the final RFB decision maker.

### Perl's Core Developers

There are several references in this RFB to "core developers". This refers to
the currently active Perl core team members. <-- TODO Define where this list and the CRUD process.

### Pumpking-Delegate

This is a role delegated by the Pumpking who has authority to made decisions
related to 1 or more RFBs.

### RFB Editors

The RFB editors are individuals responsible for managing the administrative
and editorial aspects of the RFB workflow (e.g. assigning RFB numbers and
changing their status).  See [RFB Editor Responsibilities & Workflow](#rfb-editor-responsibilities--workflow) for
details.

RFB editorship is by invitation of the current editors, and they can be
contacted by mentioning `@perl/rfb-editors` on GitHub.  All of the RFB
workflow can be conducted via the GitHub [RFB repository](http://github.com/perl/rfb) issues and pull
requests.



## Start with an idea for Perl

The RFB process begins with a new idea for Perl.  It is highly
recommended that a single RFB contain a single key proposal or new
idea. Small enhancements or patches often don't need
a RFB and can be injected into the Perl development workflow with a
[pull request](https://github.com/perl/perl5/pulls). The more focused the
RFB, the more successful it tends to be. The RFB editors reserve the
right to reject RFB proposals if they arfbar too unfocused or too
broad. If in doubt, split your RFB into several well-focused ones.

Each RFB must have a champion -- someone who writes the RFB using the style
and format described below, shepherds the discussions in the appropriate
forums, and attempts to build community consensus around the idea.  The RFB
champion (a.k.a. Author) should first attempt to ascertain whether the idea is
RFB-able. Posting to the [Perl 5 Porters mailing list](https://lists.perl.org/list/perl5-porters.html) (P5P)
is the best way to go about this.

Vetting an idea publicly before going as far as writing a RFB is meant
to save the potential author time. Many ideas have been brought
forward for changing Perl that have been rejected for various
reasons. Asking the Perl community first if an idea is original
helps prevent too much time being spent on something that is
guaranteed to be rejected based on prior discussions (searching
the internet does not always do the trick). It also helps to make sure
the idea is applicable to the entire community and not just the author.
Just because an idea sounds good to the author does not
mean it will work for most people in most areas where Perl is used.

Once the champion has asked the Perl community as to whether an
idea has any chance of acceptance, a draft RFB should be presented to
P5P. This gives the author a chance to flesh out the draft
RFB to make properly formatted, of high quality, and to address
initial concerns about the proposal.

## Submitting a RFB

Following a discussion on P5P, the workflow varies based on whether
any of the RFB's co-authors are core developers. If one or more of the RFB's
co-authors are core developers, they are responsible for following the process
outlined below. Otherwise (i.e. none of the co-authors are core developers),
then the RFB author(s) will need to find a sponsor for the RFB.

Ideally, a core developer sponsor is identified, but non-core sponsors may also
be selected with the approval of the Pumpking.  The sponsor's job is to
provide guidance to the RFB author to help them through the logistics of the
RFB process (somewhat acting like a mentor).  Being a sponsor does **not**
disqualify that person from becoming a co-author later on.  The sponsor of
a RFB is recorded in the "Sponsor:" field at the top of the document.

Once the sponsor or the core developer(s) co-authoring the RFB deem the RFB
ready for submission, the proposal should be submitted as a draft RFB via a
[GitHub pull request](https://github.com/perl/rfb/pulls).  The draft must be
written in RFB style as described below, else it will fail review immediately
(although minor errors may be corrected by the editors).

The standard RFB workflow is:

* You, the RFB author, fork the [RFB repository](http://github.com/perl/rfb), and create a file named
  `9999-rfb.md` that contains your new RFB.  Use "9999" as your draft RFB
  number.

* In the "Type:" header field, enter "Standards Track",
  "Informational", or "Process" as appropriate, and for the "Status:"
  field enter "Draft".  For full details, see [RFB Header Preamble](#RFB-Header-Preamble).

* Push this to your GitHub fork and submit a pull request.

* The RFB editors review your PR for structure, formatting, and other
  errors.
  
Approval criteria are:

  * It sound and complete.  The ideas must make technical sense.  The
    editors do not consider whether they seem likely to be accepted.
  * The title accurately describes the content.
  * The RFB's language (spelling, grammar, sentence structure, etc.)
    should be correct and conformant.

  Editors are generally quite lenient about this initial review,
  expecting that problems will be corrected by the reviewing process.
  **Note:** Approval of the RFB is no guarantee that there are no
  embarrassing mistakes!  Correctness is the responsibility of authors
  and reviewers, not the editors.

  If the RFB isn't ready for approval, an editor will send it back to
  the author for revision, with specific instructions.

* Once approved, they will assign your RFB a number.

Once the review process is complete, and the RFB editors approve it (note that
this is *not* the same as accepting your RFB!), they will squash commit your
pull request onto master.

The RFB editors will not unreasonably deny publication of a RFB.  Reasons for
denying RFB status include duplication of effort, being technically unsound,
not providing proper motivation or addressing backwards compatibility, or not
in keeping with the Perl philosophy.  The Pumpking can be consulted during
the approval phase, and is the final arbiter of a draft's RFB-ability.

Developers with git push privileges for the [RFB repository](http://github.com/perl/rfb) may claim RFB
numbers directly by creating and committing a new RFB. When doing so, the
developer must handle the tasks that would normally be taken care of by the
RFB editors. This includes ensuring the initial version meets the expected standards for submitting a
RFB.  Alternately, even developers should submit RFBs via pull request.
When doing so, you are generally expected to handle the process yourself;
if you need assistance from RFB editors, mention `@perl/rfb-editors`
in issues or pull requests on GitHub.

As updates are necessary, the RFB author can check in new versions if they
(or a collaborating developer) have git push privileges.

After a RFB number has been assigned, a draft RFB may be discussed further on
P5P (getting a RFB number assigned early can be useful for ease of
reference, especially when multiple draft RFBs are being considered at the
same time). Eventually, all Standards Track RFBs must be sent to the
perl-core list for review as described in the next section.

Standards Track RFBs consist of two parts, a design document and a
reference implementation. It is generally recommended that at least a
prototype implementation be co-developed with the RFB, as ideas that sound
good in principle sometimes turn out to be impractical when subjected to the
test of implementation.

RFB authors are responsible for collecting community feedback on a RFB
before submitting it for review. However, wherever possible, long
open-ended discussions on public mailing lists should be avoided.
Strategies to keep the discussions efficient include: setting up a
separate SIG mailing list for the topic, having the RFB author accept
private comments in the early design phases, setting up a wiki page, etc.
RFB authors should use their discretion here.

## RFB Review & Resolution

Once the authors have completed a RFB, they may request a review for
style and consistency from the RFB editors.

However, content review and final acceptance of the RFB must be requested of the
core developers, usually via an email to the perl-core mailing list.

To expedite the process in selected cases (e.g. when a change is clearly
beneficial and ready to be accepted, but the RFB hasn't been formally submitted
for review yet), the Pumpking may also initiate a RFB review, first
notifying the RFB author(s) and giving them a chance to make revisions.

The final authority for RFB approval is the Pumpking. However, whenever
a new RFB is put forward, any core developer that believes they are suitably
experienced to make the final decision on that RFB may offer to serve as
the Pumpking-Delegate for that RFB, and they will then have the authority to approve
(or reject) that RFB. Individuals taking on this responsibility are free to seek
additional guidance from the Pumpking at any time, and are also expected
to take the advice and perspectives of other core developers into account.

The designated decision maker for each RFB is recorded in the "Pumpking-Delegate"
header in the RFB.

Such self-nominations are accepted by default, but may be explicitly declined by
the Pumpking. Possible reasons for the Pumpking declining a
self-nomination as Pumpking-Delegate include, but are not limited to, perceptions of
a potential conflict of interest (e.g. working for the same organisation as the
RFB submitter), or simply considering another potential Pumpking-Delegate to be
more appropriate. If core developers (or other community members) have concerns
regarding the suitability of a Pumpking-Delegate for any given RFB, they may ask
the Pumpking to review the delegation.

If no volunteer steps forward, then the Pumpking will approach core
developers (and potentially other Perl community members) with relevant
expertise, in an attempt to identify a candidate that is willing to serve as
Pumpking-Delegate for that RFB. If no suitable candidate can be found, then the
RFB will be marked as Deferred until one is available.

Previously appointed Pumpking-Delegates may choose to step down, or be asked to step
down by the Council, in which case a new Pumpking-Delegate will be appointed in the
same manner as for a new RFB (including deferral of the RFB if no suitable
replacement can be found). In the event that a Pumpking-Delegate is asked to step
down, this will overrule any prior acceptance or rejection of the RFB, and it
will revert to Draft status.

With the approval of the Pumpking, RFB review and resolution may also
occur on a list other than P5P. In these cases, the "Discussions-To" heading in the
RFB will identify the appropriate alternative list where discussion, review and
pronouncement on the RFB will occur.

When such standing delegations are put in place, the Pumpking will
maintain sufficient public records to allow the core developers, and the wider
Perl community to understand the delegations that currently exist, why they were
put in place, and the circumstances under which they may no longer be needed.

For a RFB to be accepted it must meet certain minimum criteria. It
must be a clear and complete description of the proposed enhancement.
The enhancement must represent a net improvement.  The proposed
implementation, if applicable, must be solid and must not complicate
the interpreter unduly.

Once a RFB has been accepted, the reference implementation must be
completed.  When the reference implementation is complete and incorporated
into the main source code repository, the status will be changed to "Final".

To allow gathering of additional design and interface feedback before committing
to long term stability for a language feature or standard library API, a RFB
may also be marked as "Provisional". This is short for "Provisionally Accepted",
and indicates that the proposal has been accepted for inclusion in the reference
implementation, but additional user feedback is needed before the full design
can be considered "Final". Unlike regular accepted RFBs, provisionally accepted
RFBs may still be Rejected or Withdrawn *even after the related changes have
been included in a Perl release*.

Wherever possible, it is considered preferable to reduce the scope of a proposal
to avoid the need to rely on the "Provisional" status (e.g. by deferring some
features to later RFBs), as this status can lead to version compatibility
challenges in the wider Perl ecosystem.

A RFB can also be assigned the status "Deferred".  The RFB author or an
editor can assign the RFB this status when no progress is being made
on the RFB.  Once a RFB is deferred, a RFB editor can re-assign it
to draft status.

A RFB can also be "Rejected".  Perhaps after all is said and done it
was not a good idea.  It is still important to have a record of this
fact. The "Withdrawn" status is similar - it means that the RFB author
themselves has decided that the RFB is actually a bad idea, or has
accepted that a competing proposal is a better alternative.

When a RFB is Accepted, Rejected or Withdrawn, the RFB should be updated
accordingly. In addition to updating the status field, at the very least
the Resolution header should be added with a link to the relevant post
in the P5P mailing list archives.

RFBs can also be superseded by a different RFB, rendering the original
obsolete.  This is intended for Informational RFBs, where version 2 of
an API can replace version 1.

Some Informational and Process RFBs may also have a status of "Active"
if they are never meant to be completed.  E.g. RFB 1 (this RFB).


## RFB Maintenance

In general, Standards track RFBs are no longer modified after they have
reached the Final state. Once a RFB has been completed, the Language and
Standard Library References become the formal documentation of the expected
behavior.

If changes based on implementation experience and user feedback are made to
Standards track RFBs while in the Accepted or Provisional State, those changes
should be noted in the RFB, such that the RFB accurately describes the state of
the implementation at the point where it is marked Final.

Informational and Process RFBs may be updated over time to reflect changes
to development practices and other details. The precise process followed in
these cases will depend on the nature and purpose of the RFB being updated.



## What belongs in a successful RFB?

Each RFB should have the following parts/sections:

1. Preamble -- RFC 822 style headers containing meta-data about the
   RFB, including the RFB number, a short descriptive title (limited
   to a maximum of 44 characters), the names, and optionally the
   contact info for each author, etc.

2. Abstract -- a short (~200 word) description of the technical issue
   being addressed.

3. Motivation -- The motivation is critical for RFBs that want to
   change the Perl language, library, or ecosystem.  It should
   clearly explain why the existing language specification is
   inadequate to address the problem that the RFB solves.  RFB
   submissions without sufficient motivation may be rejected outright.

4. Rationale -- The rationale fleshes out the specification by
   describing why particular design decisions were made.  It should
   describe alternate designs that were considered and related work,
   e.g. how the feature is supported in other languages.

   The rationale should provide evidence of consensus within the
   community and discuss important objections or concerns raised
   during discussion.

5. Specification -- The technical specification should describe the
   syntax and semantics of any new language feature.

6. Backwards Compatibility -- All RFBs that introduce backwards
   incompatibilities must include a section describing these
   incompatibilities and their severity. The RFB must explain how the
   author proposes to deal with these incompatibilities. RFB
   submissions without a sufficient backwards compatibility treatise
   may be rejected outright.

7. Security Implications -- If there are security concerns in relation
   to the RFB, those concerns should be explicitly written out to make
   sure reviewers of the RFB are aware of them.

8. How to Teach This -- For a RFB that adds new functionality or changes
   language behavior, it is helpful to include a section on how to
   teach users, new and experienced, how to apply the RFB to their
   work.

   This section may include key points and recommended documentation
   changes that would help users adopt a new feature or migrate their
   code to use a language change.

9. Reference Implementation -- The reference implementation must be
   completed before any RFB is given status "Final", but it need not
   be completed before the RFB is accepted.  While there is merit
   to the approach of reaching consensus on the specification and
   rationale before writing code, the principle of "rough consensus
   and running code" is still useful when it comes to resolving many
   discussions of API details.

   The final implementation must include test code and documentation
   appropriate for either the Perl language reference or the
   standard library reference.

10. Rejected Ideas -- Throughout the discussion of a RFB, various ideas
    will be proposed which are not accepted. Those rejected ideas should
    be recorded along with the reasoning as to why they were rejected.
    This both helps record the thought process behind the final version
    of the RFB as well as preventing people from bringing up the same
    rejected idea again in subsequent discussions.

    In a way this section can be thought of as a breakout section of the
    Rationale section that is focused specifically on why certain ideas
    were not ultimately pursued.

11. Open Issues -- While a RFB is in draft, ideas can come up which
    warrant further discussion. Those ideas should be recorded so people
    know that they are being thought about but do not have a concrete
    resolution. This helps make sure all issues required for the RFB to be
    ready for consideration are complete complete and reduces people
    duplicating prior discussion.

12. References -- A collection of URLs used as references through the RFB.

13. Copyright/license: `This document is placed in the public domain or under the CC0-1.0-Universal license, whichever is more permissive.`

## RFB Formats and Templates

RFBs are UTF-8 encoded text files using the markdown format.

The RFB text files are automatically converted to HTML for easier online reading https://.../dev/RFBs/


RFB Header Preamble
===================

Each RFB must begin with an RFC 822 style header preamble.  The headers
must arfbar in the following order.  Headers marked with `**Optional**` are
optional and are described below.  All other headers are required. ::

```
* RFB: <rfb number>
* Title: <rfb title>
* Author: <list of authors' real names and optionally, email addrs>
* Sponsor: <real name of sponsor>  **Optional**
* Pumpking-Delegate: <RFB czar's real name>  **Optional**
* Discussions-To: <email address>  **Optional**
* Status: <Draft | Active | Accepted | Provisional | Deferred | Rejected |
           Withdrawn | Final | Superseded>
* Type: <Standards Track | Informational | Process>
* Content-Type: <text/markdown>  **Optional**
* Requires: <rfb numbers>  **Optional**
* Created: <date created on, in yyyy-mm-dd format>
* Perl-Version: <version number>  **Optional**
* Post-History: <dates of postings to P5P>
* Replaces: <rfb number>  **Optional**
* Superseded-By: <rfb number>  **Optional**
* Resolution: <url>  **Optional**
```

The Author header lists the names, and optionally the email addresses
of all the authors/owners of the RFB.  The format of the Author header
value must be

    Random J. User <address@dom.ain>

if the email address is included, and just

    Random J. User

if the address is not given.

If there are multiple authors, each should be on a separate line
following RFC 2822 continuation line conventions.  Note that personal
email addresses in RFBs will be obscured as a defense against spam
harvesters.

The Sponsor field records which developer (core, or otherwise approved by the
Pumpking) is sponsoring the RFB.  If one of the authors of the RFB is a
core developer then no sponsor is necessary and thus this field should be left
out.

The Pumpking-Delegate field is used to record the individual appointed by the
Pumpking to make the final decision on whether or not to approve or
reject a RFB. (The delegate's email address is currently omitted due to a
limitation in the email address masking for reStructuredText RFBs)

*Note: The Resolution header is required for Standards Track RFBs
only.  It contains a URL that should point to an email message or
other web resource where the pronouncement about the RFB is made.*

For a RFB where final pronouncement will be made on a list other than
P5P, a Discussions-To header will indicate the mailing list
or URL where the pronouncement will occur. A temporary Discussions-To header
may also be used when a draft RFB is being discussed prior to submission for
pronouncement. No Discussions-To header is necessary if the RFB is being
discussed privately with the author, or on the P5P mailing lists.
Note that email addresses in the Discussions-To header will not be obscured.

The Type header specifies the type of RFB: Standards Track,
Informational, or Process.

The format of a RFB is specified with a Content-Type header.  The
acceptable values are "text/markdown".

The Created header records the date that the RFB was assigned a
number, while Post-History is used to record the dates of when new
versions of the RFB are posted to P5P. Both headers should be in yyyy-mm-dd format, e.g. 2020-09-03.

Standards Track RFBs will typically have a Perl-Version header which
indicates the version of Perl that the feature will be released with.
Standards Track RFBs without a Perl-Version header indicate
interoperability standards that will initially be supported through
external libraries and tools, and then potentially supplemented by a later RFB
to add support to the standard library. Informational and Process RFBs do
not need a Perl-Version header.

RFBs may have a Requires header, indicating the RFB numbers that this
RFB depends on.

RFBs may also have a Superseded-By header indicating that a RFB has
been rendered obsolete by a later document; the value is the number of
the RFB that replaces the current document.  The newer RFB must have a
Replaces header containing the number of the RFB that it rendered
obsolete.


## Auxiliary Files

RFBs may include auxiliary files such as diagrams.  Such files should be
named `rfb-XXXX-Y.ext`, where "XXXX" is the RFB number, "Y" is a
serial number (starting at 1), and "ext" is replaced by the actual
file extension (e.g. "png").

Alternatively, all support files may be placed in a subdirectory called
`rfb-XXXX`, where "XXXX" is the RFB number. When using a subdirectory, there
are no constraints on the names used in files.


## Reporting RFB Bugs, or Submitting RFB Updates

How you report a bug, or submit a RFB update depends on several
factors, such as the maturity of the RFB, the preferences of the RFB
author, and the nature of your comments.  For the early draft stages
of the RFB, it's probably best to send your comments and changes
directly to the RFB author.  For more mature, or finished RFBs you may
want to submit corrections as a [GitHub issue](https://github.com/perl/RFB/issues) or [GitHub pull request](https://github.com/perl/RFB/pulls) so that
your changes don't get lost.

When in doubt about where to send your changes, please check first
with the RFB author and/or a RFB editor.

RFB authors with git push privileges for the [RFB repository](http://github.com/perl/rfb) can update the
RFBs themselves by using "git push" or the GitHub PR interface to submit their
changes.


## Transferring RFB Ownership

It occasionally becomes necessary to transfer ownership of RFBs to a
new champion. In general, it is preferable to retain the original author as
a co-author of the transferred RFB, but that's really up to the
original author. A good reason to transfer ownership is because the
original author no longer has the time or interest in updating it or
following through with the RFB process, or has fallen off the face of
the 'net (i.e. is unreachable or not responding to email).  A bad
reason to transfer ownership is because the author doesn't agree with the
direction of the RFB. One aim of the RFB process is to try to build
consensus around a RFB, but if that's not possible, an author can always
submit a competing RFB.

If you are interested in assuming ownership of a RFB, you can also do this via
pull request.  Fork the [RFB repository](http://github.com/perl/rfb), make your ownership modification,
and submit a pull request.  You should mention both the original author and
`@perl/rfb-editors` in a comment on the pull request.  (If the original
author's GitHub username is unknown, use email.)  If the original author
doesn't respond in a timely manner, the RFB editors will make a
unilateral decision (it's not like such decisions can't be reversed).


## RFB Editor Responsibilities & Workflow

A RFB editor must be added to the `@perl/rfb-editors` group on GitHub and
must watch the [RFB repository](http://github.com/perl/rfb).

Note that developers with git push privileges for the [RFB repository](http://github.com/perl/rfb) may
handle the tasks that would normally be taken care of by the RFB editors.
Alternately, even developers may request assistance from RFB editors by
mentioning `@perl/rfb-editors` on GitHub.

For each new RFB that comes in an editor does the following:

1. Make sure that the RFB is either co-authored by a core developer, has a core
  developer as a sponsor, or has a sponsor specifically approved for this RFB
  by the Pumpking.
2. Read the RFB to check if it is ready: sound and complete.  The ideas
  must make technical sense, even if they don't seem likely to be
  accepted.
3. The title should accurately describe the content.
4. The file name extension (`.md`) is correct.
5. Skim the RFB for obvious defects in language (spelling, grammar, sentence structure, etc.). Editors may correct problems themselves, but are not required to do so.
    * If the RFB isn't ready, an editor will send it back to the author for revision, with specific instructions.
    * Once the RFB is ready for the repository, a RFB editor will:
6. Assign a RFB number (almost always just the next available number, but sometimes it's a special/joke number, like 666 or 3141).
7. Check that the author has correctly labeled the RFB's type ("Standards Track", "Informational", or "Process"), and marked its status as "Draft".
8. Add the RFB to a local fork of the [RFB repository](http://github.com/perl/rfb).
9. Commit and push the new (or updated) RFB
10. Send email back to the RFB author with next steps. Post to P5P.

Updates to existing RFBs should be submitted as a [GitHub pull request](https://github.com/perl/RFB/pulls).

Many RFBs are written and maintained by developers with write access
to the Perl codebase.  The RFB editors monitor the [RFB repository](http://github.com/perl/rfb)
for changes, and correct any structure, grammar, spelling, or
markup mistakes they see.

RFB editors don't pass judgment on RFBs.  They merely do the
administrative & editorial part (which is generally a low volume task).


## References and Footnotes

None yet.


## Copyright

This document is placed in the public domain or under the CC0-1.0-Universal license, whichever is more permissive.

