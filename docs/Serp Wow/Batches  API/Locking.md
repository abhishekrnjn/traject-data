Locking Batches
---------------

Batches can be locked to only allow searches of a specified type to be added.

![](https://apiimages.imgix.net/serpwow/images/png/docs/batch_lock_setup.png?auto=format&ixlib=react-9.5.1-beta.1&w=500)Locking a BatchLocking a Batch to a specific search type has several benefits including allowing SerpWow to automatically choose the correct CSV fields, appropriate to the searches in the Batch, to be selected by default when exporting a Result Set in CSV mode. It can also help organize your account when you have many Batches set up.

![](https://apiimages.imgix.net/serpwow/images/png/docs/batch_locked.png?auto=format&ixlib=react-9.5.1-beta.1&w=350)A locked BatchA Batch can also be left unlocked (set to `mixed`) to allow *any* search type to be added.

If you leave the Batch as unlocked SerpWow will automatically detect the search type based on the searches that have been subsequently added to the Batch (or will be set to `mixed` in the case of the Batch containing a mix of different search types).

![]()An unlocked BatchYou can specify whether a Batch is locked when setting the Batch up in the Dashboard, or via the Batches API. For more information see the [Create Batch API documentation](/docs/batches-api/batches/create).

