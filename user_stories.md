User Stories
============

Auditor/Security Officer
------------------------

As an auditor or security officer who is responsible for maintaining security
and preventing attacks, or proving the fact that a malicious activity has been
conducted by an employee or a contractor:

* I would like every protected client system to record information about who
  has accessed that system, so in case of a security incident it is easier to
  identify the culprit. This information should be emitted by the system in
  such a way that the recorded privileged user can't prevent its flow without
  leaving tracks he/she was trying to do so.
* I would like the information to be consolidated on a central server where it
  can be viewed and correlated with the authentication activity collected from
  the central authentication servers, so that I can identify and verify when
  sessions started and ended and whether they were preceded by authentication
  failures.
* I would like every command and operation that the user has ran while he/she
  was logged into the system to be recorded and delivered to the central
  server so that it can be stored safely, viewed and analyzed, and correlated
  with the activity of other users.
* I would like the activity information to be recorded and later presented in
  the most intuitive way, to be able to understand what the user was doing
  while logged into the system. The best format for such information, as
  recognized by IT professionals, is the full screen capture of the input and
  output of the user's terminal session.
* I would like to be able to better rationalize the impact of the malicious
  activity by correlating the session recording with the underlying activity
  (audit trail) recorded by the system.
* I would like to be able to view the recorded sessions in a central server
  via a web interface, since I prefer not to be bound to a specific platform
  and install a thick client.
* In some cases I would like to be able to play session back from a command
  line using a simple command line tool, so I can test the setup, or act in
  limited environments, such as system recovery modes.
* I would like to be able to watch the playback of the session, start, stop,
  rewind, scroll forward or back, play faster or slower. I would like to be
  able to pause the playback select the command that the user entered and see
  the recorded trail of the activities happening on the system (file system
  operations, socket requests, started and stopped process) that correspond to
  the selected command. This would allow me to understand the sequence of
  events within the user session quicker and easier.
* I would like to be able to keep the recorded information for playback for a
  period of time defined by my policy and capacity preferences. After that
  period the solution should overwrite, purge or archive the collected
  information depending on the configuration.
* I would like to be able to easily navigate to the recorded session so that I
  can select the right session to play back. I should be able to search
  recorded sessions and related audit data by user, user group, system and
  group of systems as well as narrow search to a specific service like SSH or
  limit the time period I am looking for the session to start (or finish). For
  example I should be able to say:
    * I want to find all the sessions by John Doe in my environment during
      this weekend
    * I want to find all administrative sessions that were recorded last week
      against my file servers in my New Jersey datacenter.

See also [user stories specific to playback UI](playback_ui_user_stories.md).

System Administrator
--------------------

As a system administrator responsible for integrating the session recording
solution into existing or new infrastructure:

* I would like to be able to control session recording locally on specific
  hosts, for specific users, without requiring SSSD or FreeIPA involvement or
  use at all, so that I can test it out, support simple installations, or
  integrate with other identity management solutions.
* I would like to be able to control session recording locally on specific
  hosts, for specific users, through already deployed SSSD, without involving
  the central identity management solution (FreeIPA or other) which controls
  it, so that I can test it out, or use it for just a few systems with lower
  management cost.
* I would like to be able to control session recording centrally via FreeIPA
  for many hosts, host groups, users or groups, so that I can save on
  maintenance costs by having all configuration done through a single
  interface, in one place.
* I would like the delivery mechanism that is used to send information from
  the client system to the central server to be scalable, reliable and support
  high-availability and load-balancing configurations.
* I would like the information that is sent from the client system, to be sent
  via protected and authenticated channel so that it can't be tampered with or
  disclosed in transit.
