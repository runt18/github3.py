.. vim: set tw=100

1.0.0: 2014-xx-xx
~~~~~~~~~~~~~~~~~

1.0.0 is a huge release. It includes a great deal of changes to ``github3.py``.
It is suggested you read the following release notes *very* carefully.

Breaking Changes
````````````````

- ``Organization#add_member`` has been changed. The second parameter has been
  changed to ``team_id`` and now expects an integer.

- ``Organization#add_repository`` has been changed. The second parameter has been
  changed to ``team_id`` and now expects an integer.

- All methods and functions starting with ``iter_`` have been renamed.

==========================================    ==============================================
Old name                                      New name
==========================================    ==============================================
``github3.iter_all_repos``                    ``github3.all_repositories``
``github3.iter_all_users``                    ``github3.all_users``
``github3.iter_events``                       ``github3.all_events``
``github3.iter_followers``                    ``github3.followers_of``
``github3.iter_following``                    ``github3.followed_by``
``github3.iter_repo_issues``                  ``github3.issues_on``
``github3.iter_orgs``                         ``github3.organizations_with``
``github3.iter_user_repos``                   ``github3.repositories_by``
``github3.iter_starred``                      ``github3.starred_by``
``github3.iter_subscriptions``                ``github3.subscriptions_for``
``Deployment#iter_statuses``                  ``Deployment#statuses``
``Gist#iter_comments``                        ``Gist#comments``
``Gist#iter_commits``                         ``Gist#commits``
``Gist#iter_files``                           ``Gist#files``
``Gist#iter_forks``                           ``Gist#forks``
``GitHub#iter_all_repos``                     ``GitHub#all_repositories``
``GitHub#iter_all_users``                     ``GitHub#all_users``
``GitHub#iter_authorizations``                ``GitHub#authorizations``
``GitHub#iter_emails``                        ``GitHub#emails``
``GitHub#iter_events``                        ``GitHub#events``
``GitHub#iter_followers``                     ``GitHub#{followers,followers_of}``
``GitHub#iter_following``                     ``GitHub#{following,followed_by}``
``GitHub#iter_gists``                         ``GitHub#{gists,gists_by,public_gists}``
``GitHub#iter_notifications``                 ``GitHub#notifications``
``GitHub#iter_org_issues``                    ``GitHub#organization_issues``
``GitHub#iter_issues``                        ``GitHub#issues``
``GitHub#iter_user_issues``                   ``GitHub#user_issues``
``GitHub#iter_repo_issues``                   ``GitHub#issues_on``
``GitHub#iter_keys``                          ``GitHub#keys``
``GitHub#iter_orgs``                          ``GitHub#{organizations,organizations_with}``
``GitHub#iter_repos``                         ``GitHub#reposistories``
``GitHub#iter_user_repos``                    ``GitHub#repositories_by``
``GitHub#iter_user_teams``                    ``GitHub#user_teams``
``Issue#iter_comments``                       ``Issue#comments``
``Issue#iter_events``                         ``Issue#events``
``Issue#iter_labels``                         ``Issue#labels``
``Milestone#iter_labels``                     ``Milestone#labels``
``Organization#iter_members``                 ``Organization#members``
``Organization#iter_public_members``          ``Organization#public_members``
``Organization#iter_repos``                   ``Organization#repositories``
``Organization#iter_teams``                   ``Organization#teams``
``PullRequest#iter_comments``                 ``PullRequest#review_comments``
``PullRequest#iter_commits``                  ``PullRequest#commits``
``PullRequest#iter_files``                    ``PullRequest#files``
``PullRequest#iter_issue_comments``           ``PullRequest#issue_comments``
``Team#iter_members``                         ``Team#members``
``Team#iter_repos``                           ``Team#repositories``
``Repository#iter_assignees``                 ``Repository#assignees``
``Repository#iter_branches``                  ``Repository#branches``
``Repository#iter_code_frequency``            ``Repository#code_frequency``
``Repository#iter_collaborators``             ``Repository#collaborators``
``Repository#iter_comments``                  ``Repository#comments``
``Repository#iter_comments_on_commit``        ``Repository#comments_on_commit``
``Repository#iter_commit_activity``           ``Repository#commit_activity``
``Repository#iter_commits``                   ``Repository#commits``
``Repository#iter_contributor_statistics``    ``Repository#contributor_statistics``
``Repository#iter_contributors``              ``Repository#contributors``
``Repository#iter_forks``                     ``Repository#forks``
``Repository#iter_hooks``                     ``Repository#hooks``
``Repository#iter_issues``                    ``Repository#issues``
``Repository#iter_issue_events``              ``Repository#issue_events``
``Repository#iter_keys``                      ``Repository#keys``
``Repository#iter_labels``                    ``Repository#labels``
``Repository#iter_languages``                 ``Repository#languages``
``Repository#iter_milestones``                ``Repository#milestones``
``Repository#iter_network_events``            ``Repository#network_events``
``Repository#iter_notifications``             ``Repository#notifications``
``Repository#iter_pages_builds``              ``Repository#pages_builds``
``Repository#iter_pulls``                     ``Repository#pull_requests``
``Repository#iter_refs``                      ``Repository#refs``
``Repository#iter_releases``                  ``Repository#releases``
``Repository#iter_stargazers``                ``Repository#stargazers``
``Repository#iter_subscribers``               ``Repository#subscribers``
``Repository#iter_statuses``                  ``Repository#statuses``
``Repository#iter_tags``                      ``Repository#tags``
``Repository#iter_teams``                     ``Repository#teams``
``Repository#iter_teams``                     ``Repository#teams``
``User#iter_events``                          ``User#events``
``User#iter_followers``                       ``User#followers``
``User#iter_following``                       ``User#following``
``User#iter_keys``                            ``User#keys``
``User#iter_org_events``                      ``User#organization_events``
``User#iter_received_events``                 ``User#received_events``
``User#iter_orgs``                            ``User#organizations``
``User#iter_starred``                         ``User#starred_repositories``
``User#iter_subscriptions``                   ``User#subscriptions``
==========================================    ==============================================

- ``github3.login`` has been simplified and split into two functions:

  - ``github3.login`` serves the majority use case and only provides an 
    authenticated ``GitHub`` object.

  - ``github3.enterprise_login`` allows GitHub Enterprise users to log into 
    their service.

- ``GitHub#iter_followers`` was split into two functions:

  - ``GitHub#followers_of`` which iterates over all of the followers of a user
    whose username you provide

  - ``GitHub#followers`` which iterates over all of the followers of the
    authenticated user

- ``GitHub#iter_following`` was split into two functions:

  - ``GitHub#followed_by`` which iterates over all of the users followed by
    the username you provide

  - ``GitHub#following`` which iterates over all of the users followed by the
    authenticated user

- ``GitHub#iter_gists`` was split into three functions:

  - ``GitHub#public_gists`` which iterates over all of the public gists on 
    GitHub

  - ``GitHub#gists_for`` which iterates over all the public gists of a 
    specific user

  - ``GitHub#gists`` which iterates over the authenticated users gists

- ``GitHub#iter_orgs`` was split into two functions:

  - ``GitHub#organizations`` which iterates over the authenticated user's
    organization memberships

  - ``GitHub#organizations_with`` which iterates over the given user's
    organization memberships

- ``GitHub#iter_subscriptions`` was split into two functions:

  - ``GitHub#subscriptions_for`` which iterates over an arbitrary user's
    subscriptions

  - ``GitHub#subscriptions`` which iterates over the authenticated user's 
    subscriptions

- ``GitHub#iter_starred`` was split into two functions:

  - ``GitHub#starred_by`` which iterates over an arbitrary user's stars

  - ``GitHub#starred`` which iterates over the authenticated user's stars

- ``GitHub#user`` was split into two functions:

  - ``GitHub#user`` which retrieves an arbitrary user's information

  - ``GitHub#me`` which retrieves the authenticated user's information

- The legacy watching API has been removed:

  - ``GitHub#subscribe``

  - ``GitHub#unsubscribe``

  - ``GitHub#is_subscribed``

- ``GitHub#create_repo`` was renamed to ``GitHub#create_repository``

- ``GitHub#delete_key`` was removed. To delete a key retrieve it with
  ``GitHub#key`` and then call ``Key#delete``.

- ``Repository#set_subscription`` was split into two simpler functions

  - ``Repository#subscribe`` subscribes the authenticated user to the 
    repository's notifications

  - ``Repository#ignore`` ignores notifications from the repository for the 
    authenticated user

- ``Organization#add_repo`` and ``Team#add_repo`` have been renamed to
  ``Organization#add_repository`` and ``Team#add_repository`` respectively.

- ``Organization#create_repo`` has been renamed to
  ``Organization#create_repository``. It no longer accepts ``has_downloads``.
  It now accepts ``license_template``.

- ``Organization#remove_repo`` has been renamed to
  ``Organization#remove_repository``. It now accepts ``team_id`` instead of
  ``team``.

- ``github3.ratelimit_remaining`` was removed

- ``GitHub`` instances can no longer be used as context managers

- The pull request API has changed.

  - The ``links`` attribute now contains the raw ``_links`` attribute from the
    API.

  - The ``merge_commit_sha`` attribute has been removed since it was deprecated
    in the GitHub API.

  - To present a more consistent universal API, certain attributes have been
    renamed.

===============================     ==========================
Old name                            New attribute name
===============================     ==========================
``PullFile.additions``              ``additions_count``
``PullFile.deletions``              ``deletions_count``
``PullFile.changes``                ``changes_count``
``PullRequest.additions``           ``additions_count``
``PullRequest.comments``            ``comments_count``
``PullRequest.commits``             ``commits_count``
``PullRequest.deletions``           ``deletions_count``
``PullRequest.review_comments``     ``review_comments_count``
===============================     ==========================

- The Gist API has changed.

  - The ``forks`` and ``files`` attributes that used to keep count of the
    number of ``forks`` and ``files`` have been **removed**.

  - The ``comments`` attribute which provided the number of comments on a
    gist, has been **renamed** to ``comments_count``.

  - The ``is_public`` method has been removed since it just returned the
    ``Gist.public`` attribute.

- Most instances of ``login`` as a parameter have been changed to ``username``
  for clarity and consistency. This affects the following methods:

    - ``github3.authorize``
    - ``github3.repositories_by``
    - ``github3.user``
    - ``GitHub``
    - ``GitHub#authorize``
    - ``GitHub#follow``
    - ``GitHub#is_following``
    - ``GitHub#is_starred``
    - ``GitHub#issue``
    - ``GitHub#followers_of``
    - ``GitHub#followed_by``
    - ``GitHub#gists_by``
    - ``GitHub#issues_on``
    - ``GitHub#organizations_with``
    - ``GitHub#starred_by``
    - ``GitHub#subscriptions_for``
    - ``GitHub#user``
    - ``GitHubEnterprise``
    - ``Issue#assign``
    - ``Organization#add_member``
    - ``Organization#is_member``
    - ``Organization#is_public_member``
    - ``Organization#remove_member``
    - ``Repository#add_collaborator``
    - ``Repository#is_assignee``
    - ``Repository#is_collaborator``
    - ``Repository#remove_collaborator``
    - ``Team#add_member``
    - ``Team#is_member``
    - ``User#is_assignee_on``
    - ``User#is_following``

- ``Repository.stargazers`` is now ``Repository.stargazers_count`` (conforming
  with the attribute name returned by the API).


- The ``Issue`` API has changed in order to provide a more consistent attribute
  API. ``Issue.comments`` is now ``Issue.comments_count`` and returns the
  number of comments on an issue.

- The ``Issue.labels`` attribute has also been renamed. It is now available from
  ``Issue.original_labels``. This will provide the user with the list of
  ``Label`` objects that was returned by the API. To retrieve an updated list
  of labels, the user can now use ``Issue#labels``, e.g.

  ::

      i = github3.issue('sigmavirus24', 'github3.py', 30)
      labels = list(i.labels())

- The ``Organization`` and ``User`` APIs have changed to become more
  consistent with the rest of the library and GitHub API. The following
  attribute names have been changed

===============================     ==========================
Old name                            New attribute name
===============================     ==========================
``Organization.followers``          ``followers_count``
``Organization.following``          ``following_count``
``Organization.public_repos``       ``public_repos_count``
``User.followers``                  ``followers_count``
``User.following``                  ``following_count``
``User.public_repos``               ``public_repos_count``
===============================     ==========================

- The ``Release.assets`` attribute has been renamed to
  ``Release.original_assets``. To retrieve up-to-date assets, use the
  ``Release#assets`` method.

- The ``Authorization`` API has changed. The ``update`` method has been split
  into three methods: ``add_scopes``, ``remove_scopes``, ``replace_scopes``.
  This highlights the fact that ``Authorization#update`` used to require more
  than one request.

- ``Event#is_public`` has been removed. Simply check the event's ``public``
  attribute instead.

New Features
````````````

- Most objects now have a ``session`` attribute. This is a subclass of a
  ``Session`` object from ``requests``. This can now be used in conjunction
  with a third-party caching mechanism. The suggested caching library is
  ``cachecontrol``.

- All object's ``url`` attribute are now available.

- You can now retrieve a repository by its id with
  ``GitHub#repository_with_id``.