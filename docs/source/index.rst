.. Trio documentation master file, created by
   sphinx-quickstart on Sat Jan 21 19:11:14 2017.
   You can adapt this file completely to your liking, but it should at least
   contain the root `toctree` directive.

===================================================
Trio: async programming for humans and snake people
===================================================

*「APIはuser interfaceそのもの」Kenneth Reitzの言葉*

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

Vital statistics:

* 対応している環境: Python3.5以上(CPythonとPyPy3どちらでも可)が入っている
Linux、macOS、Windows。BSDとillumos系も動くはずですがtestはしてません。

* install方法: ``python3 -m pip install -U trio`` (Windowsだと
  ``py -3 -m pip install -U trio`` かもしれません)。何かcompilerが要ったりはしません.

* tutorialとreference manual: https://trio.readthedocs.io

* source code: https://github.com/python-trio/trio

* real-time chat: https://gitter.im/python-trio/general

* 利用規約: MITかApache2のいずれか好きな方

* projectに貢献したい時: https://trio.readthedocs.io/en/latest/contributing.html

* Code of conduct: Contributors are requested to follow our `code of
  conduct
  <https://trio.readthedocs.io/en/latest/code-of-conduct.html>`_
  in all project spaces.


.. toctree::
   :maxdepth: 2
   :caption: Trio's friendly, yet comprehensive, manual:

   tutorial.rst
   reference-core.rst
   reference-io.rst
   reference-testing.rst
   reference-hazmat.rst
   design.rst
   history.rst
   contributing.rst
   releasing.rst
   code-of-conduct.rst

====================
 Indices and tables
====================

* :ref:`genindex`
* :ref:`modindex`
* :ref:`search`
* :ref:`glossary`
