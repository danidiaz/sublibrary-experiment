
https://discourse.haskell.org/t/testing-a-library-that-depends-on-downstream-packages/4541/3

The ["public sublibraries"](https://github.com/haskell/cabal/issues/5660) feature of Cabal seems to be still experimental at the moment. I don't know about Hackage support either.

Invoking `cabal build wumpus-json:lib:wumpus-json` doesn't seem to build "wumpus-test-support", which is good.

However, adding a bogus dependency to the `build-depends:` of "wumpus-test-support" (like "aeson >= 13.0.0.0") and then running `cabal build wumpus-json:lib:wumpus-json` fails, wich is a bit unsatisfactory, because it means that the main `wumpus` library is still saddled with all the exptra dependencies of "wumpus-test-support".

