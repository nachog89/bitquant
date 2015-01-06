CHOICE OF LANGUAGE

We ended up using javascript for the language.  Originally, we were
going to use python because that is the standard language in banks.
However, the lenders stated that they prefered javascript, which makes
sense because javascript is very well known in web development, and
allowed us to create a web app.

One problem with javascript is that all numbers are floats, and you
don't have operator overloading.  In Python, you can create a money
class which makes multicurrency easy.  Also in javascript, all dates
have time zone associated with them which is something a bad thing.

For libraries what wanted to remove any libraries from the term sheet
itself.  Also we used requirejs to make it work with both nodejs and
with a web browser.  I considered having a javascript compiled
language like coffeescript, but the extra overhead in the compiler was
problematic.

ANNOYANCES

Markdown uses two spaces to separate paragraphs.

COMMENTS

One of the legal issues was to carefully divide what is commentary and
what is legally enforceable.  In particular, the TermSheet.js file
does not contain any comments, because this would create confusion
over whether the code is the contract or the comments are in the
contract.

To deal with this issue, all of the comments are in a side notes.  The
side note contains representations from from the borrower to the
lender regarding the content of the code.  However this agreement is
separate from the contract itself.

What we expect to happen is that if there is a substantive conflict
between the terms of the contract and the notes, that this would be
handled under the law of mistake or misrepresentation.  However, this
would only cover the original borrower and lender.  If the loan is
resold, any representations would not cover that situation.

It's also important that the contract analyzer is not part of the
contract itself.

IP OF CONTRACT

One conflict was between software conventions for IP rights and lawyer
conventions.  In software, the IP rights are always very clear.
Either there is an open source license or the license is proprietary.
Also software developers are very careful about IP issues and there is
invariably an agreement as to who owns IP rights to the work.

With lawyers the question of who owns the IP to the contract text is
usually not explicitly stated, and the practice seems to be that
lawyers allow a text to circulate, but never renounce ownership of
copyright, and reserve the right to assert IP at a later time.
Lawyers will also rarely explicitly define IP rights for contract
text, as the contract is often not reusable anyway, and you end up
with "meta"-problems (i.e. who do you consult to negotiate a contract
with a lawyer).

This practice will not work for software products, as it create a
situation in which IP is unclear.  This creates an problem with "clean
title."

Unfortunately, the statuory law is unclear about what happens in this
situation.  The issue is that different jurisdictions have different
legal systems.  In Hong Kong, this is covered under section ?? of the
Copyright Ordinance and is clearly a commissioned work in which the
lawyer retains copyright ownership, whereas the person that
commissioned the work retains an *exclusive* license to use the work.
There are two issues here.  The first is that this is an HK only
situation, this would clearly not be a commissioned work under US or
UK law and the Berne Convention is silent on this issue.

It's also unclear how moral rights play into this.  Under HK law,
software is not subject to moral rights.  However, is this software?

The solution in this case was that the lender paid the legal firm that
drafted the contract a large sum of money in exchange for an
assignment of copyright, which allows for a template contract to be
published under a BSD license.  It's worth noting that the executed
contract will not be BSD licensed, because you explicitly *don't* want
to disclaim liability.

PRIVACY ISSUES

One problem is what is public and what is private.  The fact that a
company is getting a loan is sensitive information that you won't want
to spread around.  So what we did was to put the public template
contract on github.  The exact amounts and the identities of the
borrower and lender are not included.

BUGS

It's worth noting that writing the contract in javascript allowed for
removing some ambiguity in the contract.  For example, in calculating
the accelerated payment, you run into the question of what happens if
you hit two targets on the same day.  Also, when writing up the
contract, you have the question of what happens if someone pays off
the contract, can they keep the credit limit?  If someone has a late
interest rate, does this apply to only the late balance or the whole
balance?


