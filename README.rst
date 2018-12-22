.. image:: https://img.shields.io/badge/chat-join%20now-blue.svg
   :target: https://gitter.im/python-trio/general
   :alt: Join chatroom

.. image:: https://img.shields.io/badge/docs-read%20now-blue.svg
   :target: https://trio.readthedocs.io/en/latest/?badge=latest
   :alt: Documentation Status

.. image:: https://img.shields.io/pypi/v/trio.svg
   :target: https://pypi.org/project/trio
   :alt: Latest PyPi version

.. image:: https://img.shields.io/conda/vn/conda-forge/trio.svg
   :target: https://anaconda.org/conda-forge/trio
   :alt: Latest conda-forge version

.. image:: https://travis-ci.org/python-trio/trio.svg?branch=master
   :target: https://travis-ci.org/python-trio/trio
   :alt: Automated test status (Linux and macOS)

.. image:: https://ci.appveyor.com/api/projects/status/af4eyed8o8tc3t0r/branch/master?svg=true
   :target: https://ci.appveyor.com/project/njsmith/trio/history
   :alt: Automated test status (Windows)

.. image:: https://codecov.io/gh/python-trio/trio/branch/master/graph/badge.svg
   :target: https://codecov.io/gh/python-trio/trio
   :alt: Test coverage

Trio – async I/O for humans and snake people
============================================

*「APIはuser interfaceそのもの」Kenneth Reitzの言葉*

.. Github carefully breaks rendering of SVG directly out of the repo,
   so we have to redirect through cdn.rawgit.com
   See:
     https://github.com/isaacs/github/issues/316
     https://github.com/github/markup/issues/556#issuecomment-288581799
   I also tried rendering to PNG and linking to that locally, which
   "works" in that it displays the image, but for some reason it
   ignores the width and align directives, so it's actually pretty
   useless...

.. image:: https://cdn.rawgit.com/python-trio/trio/9b0bec646a31e0d0f67b8b6ecc6939726faf3e17/logo/logo-with-background.svg
   :width: 200px
   :align: right

このprojectのgoalは、高品質で
`license <https://github.com/python-trio/trio/blob/master/LICENSE>`__
が寛容でasync/await構文の使えるPython向けの非同期入出力libraryを作ることです。
Trioも他の非同期libraryと同じで複数の入出力を並行して行うcodeを書くのを助けてくれます。
例えば 大量のpageを並行して落とす必要のあるweb収集program、
大量のdownload要求や接続要求に応えるweb server、複数の子processを管理する親process等です。
またTrioは使いやすさに重きを置く事で他のlibraryとの差別化を図ろうとしています。
一般的に並行処理は複雑なものですから、これを簡単に正確に書けるようにしたいのです。

Trioは
`async/await構文 <https://www.python.org/dev/peps/pep-0492/>`__
の持つ利点を基に築かれいて、また
`他の様々な物 <https://github.com/python-trio/trio/wiki/Reading-list>`__
から影響を受けています。(特にDave Beazleyさんの
`Curio <https://curio.readthedocs.io/>`__
)。
その結果
`asyncio <https://docs.python.org/3/library/asyncio.html>`__
や
`Twisted <https://twistedmatrix.com/>`__
のような古参と比べると、最低限の機能は持ちながらも圧倒的に簡素なAPIに仕上がっています。
このTrioこそが私が常に欲していたPython用入出力libraryなのです。
I find it makes building
I/O-oriented programs easier, less error-prone, and just plain more
fun. Perhaps you'll find the same.

このprojectはまだ始まったばかりで実験段階です。
全体の構想は固まっていて実装済の機能は完全にtestされていて文書化もされていますが、
時々欲しい機能が無かったり荒削りな部分に出遭ったりするかもしれません。
それでも私達はTrioを使うことを応援しますが、まず最初に
`issue #1 <https://github.com/python-trio/trio/issues/1>`__
を購読するのを忘れないでください。
互換性の無いAPI変更に関する情報をそこで得られます。


次は何する?
------

「 **実際に使ってみたい!** 」
いいね! 始めるならここに
`易しいtutorial <https://trio.readthedocs.io/en/latest/tutorial.html>`__
があるよ。非同期programmingの経験が無くても読めるから安心してね。

「 **ええ！？これ全部読むのしんどいよ。とにかくcodeを見せてくれ** 」
せっかくの素晴らしいtutorialなのに！でもどうしてもと言うなら

`simple concurrency example <https://trio.readthedocs.io/en/latest/tutorial.html#tutorial-example-tasks-intro>`__ 、
`echo client <https://trio.readthedocs.io/en/latest/tutorial.html#tutorial-echo-client-example>`__ 、
`echo server <https://trio.readthedocs.io/en/latest/tutorial.html#tutorial-echo-server-example>`__ 。

「 **いいね、でもこれ僕のPCで動くの？** 」
多分ね! Python3.5以上(CPythonとPyPy3どちらでも可)を持っていて、
LinuxかMaxOSかWindowsを使ってるなら動くはずだよ。
BSDとillumos系も動くはずだけど、これらの環境用のtestはしてないよ。
依存関係の内、Windowsに必要なCFFIを除いては全て純Pythonで、CFFIにはwheelが用意されているからinstallationは簡単なはずだよ。

「 **試したけど動かなかったよ** 」
それは残念!
`chat room <https://gitter.im/python-trio/general>`__
で誰かに訊くか、
`issueを上げる <https://github.com/python-trio/trio/issues/new>`__
か
`StackOverflowで質問する <https://stackoverflow.com/questions/ask?tags=python+python-trio>`__
とかしてね。

「 **Trio最高だよ。もっと良くする為に何か貢献したい!** 」
You're the best! There's tons of work to do – filling in missing
functionality, building up an ecosystem of trio-using libraries,
usability testing (e.g., maybe try teaching yourself or a friend to
use trio and make a list of every error message you hit and place
where you got confused?), improving the docs, ... check out our `guide
for contributors
<https://trio.readthedocs.io/en/latest/contributing.html>`__!

「 **別にこれを使う予定があるわけじゃないけど、入出力libraryのdesignに興味がある!** 」
That's a little weird? But tbh you'll fit
in great around here. Check out our `discussion of design choices
<https://trio.readthedocs.io/en/latest/design.html#user-level-api-principles>`__,
`reading list
<https://github.com/python-trio/trio/wiki/Reading-list>`__, and
`issues tagged design-discussion
<https://github.com/python-trio/trio/labels/design%20discussion>`__。

「 **利用規約は？** 」
心配ないよ。TrioはMITとApache2のどちらか好きな方のlicenseで使えるよ。
詳しくは
`LICENSE <https://github.com/python-trio/trio/blob/master/LICENSE>`__
を見てね。


..
   next:
   - @_testing for stuff that needs tighter integration? kinda weird
     that wait_all_tasks_blocked is in hazmat right now

     and assert_checkpoints stuff might make more sense in core

   - make @trio_test accept clock_rate=, clock_autojump_threshold=
     arguments
     and if given then it automatically creates a clock with those
     settings and uses it; can be accessed via current_clock()
     while also doing the logic to sniff for a clock fixture
     (and of course error if used kwargs *and* a fixture)

   - a thought: if we switch to a global parkinglot keyed off of
     arbitrary hashables, and put the key into the task object, then
     introspection will be able to do things like show which tasks are
     blocked on the same mutex. (moving the key into the task object
     in general lets us detect which tasks are parked in the same lot;
     making the key be an actual synchronization object gives just a
     bit more information. at least in some cases; e.g. currently
     queues use semaphores internally so that's what you'd see in
     introspection, not the queue object.)

     alternatively, if we have an system for introspecting where tasks
     are blocked through stack inspection, then maybe we can re-use
     that? like if there's a magic local pointing to the frame, we can
     use that frame's 'self'?

   - add nursery statistics? add a task statistics method that also
     gives nursery statistics? "unreaped tasks" is probably a useful
     metric... maybe we should just count that at the runner
     level. right now the runner knows the set of all tasks, but not
     zombies.

     (task statistics are closely related)

   - make sure to @ki_protection_enabled all our __(a)exit__
     implementations. Including @asynccontextmanager! it's not enough to
     protect the wrapped function. (Or is it? Or maybe we need to do
     both? I'm not sure what the call-stack looks like for a
     re-entered generator... and ki_protection for async generators is
     a bit of a mess, ugh. maybe ki_protection needs to use inspect to
     check for generator/asyncgenerator and in that case do the local
     injection thing. or maybe yield from.)

     I think there is an unclosable loop-hole here though b/c we can't
     enable @ki_protection atomically with the entry to
     __(a)exit__. If a KI arrives just before entering __(a)exit__,
     that's OK. And if it arrives after we've entered and the
     callstack is properly marked, that's also OK. But... since the
     mark is on the frame, not the code, we can't apply the mark
     instantly when entering, we need to wait for a few bytecode to be
     executed first. This is where having a bytecode flag or similar
     would be useful. (Or making it possible to attach attributes to
     code objects. I guess I could violently subclass CodeType, then
     swap in my new version... ugh.)

     I'm actually not 100% certain that this is even possible at the
     bytecode level, since exiting a with block seems to expand into 3
     separate bytecodes?

   - possible improved robustness ("quality of implementation") ideas:
     - if an abort callback fails, discard that task but clean up the
       others (instead of discarding all)
     - if a clock raises an error... not much we can do about that.

   - trio
     http://infolab.stanford.edu/trio/ -- dead for a ~decade
     http://inamidst.com/sw/trio/ -- dead for a ~decade


このprojectの規則
------------

`これ <https://trio.readthedocs.io/en/latest/code-of-conduct.html>`__
に従ってね。
