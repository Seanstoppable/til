I recently came across wanting to treat an array like a set.

I was able to do this as follows:

for a schema like

```
create table identifiers (
  name text,
  identifiers text[]
)
```

```
update identifiers
set identifiers = (select array_agg(distinct items)
	      FROM user_identifiers,
	      UNNEST(array_append(user_identifiers.identifiers, new_identifiers::text)) as items
	      where name = new_name;
	    );
```

array_agg will re-aggregate the items, making sure they are unique.
