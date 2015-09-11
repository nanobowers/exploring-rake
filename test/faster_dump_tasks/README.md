## Faster dump-tasks

In certain cases cases we do something time-expensive for all tasks in the rakefile - lookup something in a database, etc.

But in many times the data we're retrieving does not impact the tasks that are generated.

In this example we use <tt>Rake.application.options.show_tasks</tt> to bypass a time-expensive global operation when we run <tt>rake -T</tt>.



