# Introduction #

The bulk of our xulrunner code is not hosted here; it is hosted directly on the Mozilla project's CVS servers. These are basic instructions for downloading the source from Mozilla and applying our patchset.


# Details #

  * Familiarize yourself with the [Mozilla Build Documentation](http://developer.mozilla.org/en/docs/Build_Documentation)

  * Choose a source directory and execute the following command:

```
% cvs -d :pserver:anonymous@cvs-mirror.mozilla.org:/cvsroot co -r FIREFOX_3_0_1_RELEASE mozilla/client.mk mozilla/xulrunner/config/mozconfig
```

  * If doing a universal-binary Mac build, check out one more file:

```
% cvs -d :pserver:anonymous@cvs-mirror.mozilla.org:/cvsroot co -r FIREFOX_3_0_1_RELEASE mozilla/build/macosx/universal/mozconfig
```

  * Set up a .mozconfig file with appropriate options for the system that you're building the code on, per the Mozilla build instructions. Notably, MOZ\_CO\_PROJECT=xulrunner should appear in your .mozconfig file. Set the MOZCONFIG environment variable to the path to your .mozconfig.

  * Check out the bulk of the Mozilla source code. This may take a while:

```
% cd mozilla
% make -f client.mk checkout
```

  * That done, go over to the downloads page and download the patch file appropriate for your release tag (currently, patch-to-FF\_3\_0\_1\_RELEASE-for-AE-7\_6\_1.patch). Apply it to your mozilla sources as follows:

```
% patch < [path_to_downloaded_patch_file]
```

That's it! You're now ready to build xulrunner from the same source we use. Refer again to the [Mozilla Build Documentation](http://developer.mozilla.org/en/docs/Build_Documentation) if in doubt at any step of this process.

Future versions of AdWords Editor may use a Mozilla build label more current than FIREFOX\_3\_0\_1\_RELEASE. Previous build labels will be noted below.

# Old Release Labels #

  * FIREFOX\_2\_0\_0\_4\_RELEASE. (Basis for AdWords Editor version 6.0.1 and earlier)