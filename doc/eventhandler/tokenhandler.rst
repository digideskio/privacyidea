.. _tokenhandler:

Token Handler Module
--------------------

.. index:: Token Handler, Handler Modules

The token event handler module is used to perform actions on tokens in
certain events.

This way you can define workflows to automatically modify tokens, delete or
even create new tokens.

Possible Actions
~~~~~~~~~~~~~~~~

set tokenrealm
..............

Here you can set the token realms of the token.

E.g. You could use this action to automatically put all newly enrolled tokens
 into a special realm by attaching this action to the event *token_init*.

delete
......

The token which was identified in the request will be deleted if all
conditions are matched.

unassign
........

The token which was identified in the request will be unassign from the user
if all conditions are matched.

disable
.......

The token which was identified in the request will be disabled
if all conditions are matched.

enable
......

The token which was identified in the request will be enabled
if all conditions are matched.

enroll
......

If all conditions are matched a new token will be enrolled. This new token
can be assigned to a user, which was identified in the request.

The administrator can specify the **tokentype** and the **realms** of the new
 token.

set description
...............

If all conditions are matched the description of the token identified in the
request will be set.

set validity
............

If all conditions are matched the validity period of the token will be set.

There are different possibilities to set the start and the end of the
validity period. The event definition can either contain a fixed date and
time or if can contain a time offset.

**Fixed Time**

A fixed time can be specified in the following formats.

Only date without time:

  * 2016/12/23
  * 23.12.2016

Date with time:

  * 2016/12/23 9:30am
  * 2016/12/23 11:20:pm
  * 23.12.2016 9:30
  * 23.12.2016 23:20

**Time Offset**

You can also specify a time offset. In this case the validity period will be
set such many days after the event occurred. This is indicated by using a "+"
and a specifier for days (d), hours (h) and minutes (m).

E.g. ``+30m`` will set to start the validity period in 30 minutes after the
event occurred.

``+30d`` could set the validity period to end 30 days after an event occurred.

.. note:: This way you could easily define a event definition, which will set
   newly enrolled tokens to be only valid for a certain amount of days.


Code
~~~~


.. automodule:: privacyidea.lib.eventhandler.tokenhandler
   :members:
   :undoc-members:
