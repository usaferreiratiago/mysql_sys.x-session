# mysql_sys.x-session

SELECT 
    `sys`.`x$processlist`.`thd_id` AS `thd_id`,
    `sys`.`x$processlist`.`conn_id` AS `conn_id`,
    `sys`.`x$processlist`.`user` AS `user`,
    `sys`.`x$processlist`.`db` AS `db`,
    `sys`.`x$processlist`.`command` AS `command`,
    `sys`.`x$processlist`.`state` AS `state`,
    `sys`.`x$processlist`.`time` AS `time`,
    `sys`.`x$processlist`.`current_statement` AS `current_statement`,
    `sys`.`x$processlist`.`statement_latency` AS `statement_latency`,
    `sys`.`x$processlist`.`progress` AS `progress`,
    `sys`.`x$processlist`.`lock_latency` AS `lock_latency`,
    `sys`.`x$processlist`.`rows_examined` AS `rows_examined`,
    `sys`.`x$processlist`.`rows_sent` AS `rows_sent`,
    `sys`.`x$processlist`.`rows_affected` AS `rows_affected`,
    `sys`.`x$processlist`.`tmp_tables` AS `tmp_tables`,
    `sys`.`x$processlist`.`tmp_disk_tables` AS `tmp_disk_tables`,
    `sys`.`x$processlist`.`full_scan` AS `full_scan`,
    `sys`.`x$processlist`.`last_statement` AS `last_statement`,
    `sys`.`x$processlist`.`last_statement_latency` AS `last_statement_latency`,
    `sys`.`x$processlist`.`current_memory` AS `current_memory`,
    `sys`.`x$processlist`.`last_wait` AS `last_wait`,
    `sys`.`x$processlist`.`last_wait_latency` AS `last_wait_latency`,
    `sys`.`x$processlist`.`source` AS `source`,
    `sys`.`x$processlist`.`trx_latency` AS `trx_latency`,
    `sys`.`x$processlist`.`trx_state` AS `trx_state`,
    `sys`.`x$processlist`.`trx_autocommit` AS `trx_autocommit`,
    `sys`.`x$processlist`.`pid` AS `pid`,
    `sys`.`x$processlist`.`program_name` AS `program_name`
FROM
    `sys`.`x$processlist`
WHERE
    ((`sys`.`x$processlist`.`conn_id` IS NOT NULL)
        AND (`sys`.`x$processlist`.`command` <> 'Daemon'))
