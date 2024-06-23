---
title: "OpenFastTrace 2.0.0 Released"
date: 2018-10-13T20:23:59+02:00
draft: true
params:
    author: Sebastian
---

This release is a big step forward. One new feature, a few small fixes and a lot of code improvements that gives us a much cleaner and more uniform API, better test coverage and lower overall complexity.

But a new API also means we had to break backward compatibility to achieve something that the existing API would not allow since it had a separation of report and export mode: you can now reuse an import that already ran to create both reports and exports from it without redoing the import. This is a considerable speed-up (and we call the project Open**Fast**Trace for a reason. Runtime efficiency was and will always be one of our main design principles.

You can find examples of [how to use the API in the user guide](https://github.com/itsallcode/openfasttrace/blob/master/doc/user_guide.md#oft-api) and in OFTs own code of course.

Thanks to Christoph for his patience during his review of the giant change set that the API rework caused!

Enjoy the new and improved API.

Happy tracing.