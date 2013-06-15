---
published: true
layout: post
title: Introducing ok_hbase
tagline: A lightweight Ruby adapter for HBase
category: code
tags: [ok_hbase, ruby, hbase]
---

{% include JB/setup %}

## I wrote [ok_hbase](http://www.okhbase.com), a gem for using HBase from MRI Ruby, check it out:
{% highlight ruby %}
require 'ok_hbase'

# get a connection
conn = OkHbase::Connection.new(
  host: 'localhost',
  port: 9090,
  auto_connect: true
)

# create a new table with column family 'd'
table = conn.create_table('ok_hbase_test', d: {})

# put a bunch of data in the table
('hbaaa'..'hbzzz').each_with_index do |row_key, index|
  table.put(
    row_key,
    {
      'd:row_number' => "#{index+1}",
      'd:message' => "this is row number #{index+1}"
    }
  )
print "wrote row: #{row_key}\r"
end

# scan for all rows beginning with 'hba'
table.scan(row_prefix: 'hba')

# get the row with the row key 'hbase'
table.row('hbase')

# clean up
conn.delete_table('ok_hbase_test', true)
{% endhighlight %}
