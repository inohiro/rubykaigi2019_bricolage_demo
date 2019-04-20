## A bricolage demo project for RubyKaigi 2019 LT

Link to the slide: [Write ETL or ELT data processing jobs with bricolage.](https://speakerdeck.com/inohiro/write-etl-or-elt-data-processing-jobs-with-bricolage)

### How to run

```
$ rbenv install 2.5.5
$ bundle
```

Edit properly `config/development/database.yml` for local or remote PostgreSQL database.

```
# this rebuild-drop jopb generate random pv_log records
$ bundle exec bricolage -j demo/pv_log-rebuild.sql.job

# this rebuild-rename job rebuilds articles_summary table (and keeps old table)
$ bundle exec bricolage -j demo/articles_summary.sql.job
```

Or run jobnet:

```
# this does all jobs above
$ bundle exec bricolage-jobnet demo/rebuild.jobnet
```
