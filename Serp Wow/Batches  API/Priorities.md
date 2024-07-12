Batch Priorities
----------------

Batches are a great way to run a high volume of Searches without coding concurrent requests logic yourself. SerpWow allows you to [start](/docs/batches-api/batches/start) many Batches and they will be put into a `queued` state and executed sequentially.

![](https://apiimages.imgix.net/serpwow/images/png/docs/priorities.png?auto=format&ixlib=react-9.5.1-beta.1&w=500)Batch PrioritiesBy setting a `priority` to a Batch you can determine the order in SerpWow executes your queued Batches. Batches with a higher `priority` will be executed before those with a lower `priority`.

By using this method you can ensure your time-critical Batches are always executed before your "background", or non time-critical Batches.

There are 5 priority levels that can be applied to a Batch, they are:  
  
`highest`, `high`, `normal`, `low`, `lowest`.  
  
The `priority` of a Batch can be set when you [create](/docs/batches-api/batches/create) or [update](/docs/batches-api/batches/update) the Batch. If no `priority` is specified when the Batch is created it will be assigned the `normal` priority.

Batch priority does not affect the *speed* that your Batches are executed, just the order. Priorities are evaluated at the point at which the platform is going to start the next Batch. For example, if you had a Batch already running with a `normal` priority and you started another Batch with a `high` priority, the platform would still complete execution of the already-running `normal` priority Batch before starting the newly added `high` priority Batch.

Batch priority cannot be changed once the Batch is in the `queued` or `running` state, so be sure to set the desired priority before [starting](/docs/batches-api/batches/start) the Batch.

