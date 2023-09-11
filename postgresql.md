# POSTGRESQL

### NOTES

- Postgres creates a process for each connection.

### BLOG DATABASE DESIGN

#### TABLES

- users
- posts
- categories
- post_category (pivot table for posts and categories)
- comments (comment replies are stored in the same table)

#### TABLES SQL

```sql
create table users (
	id bigserial primary key, -- bigserial will create a bigint auto increment column
	name varchar(50) not null,
	email varchar(255) not null unique -- not null unique column
)

```

```sql
create table posts (
    id bigserial primary key,
	user_id bigint not null,
	title varchar(255) not null unique,
	body text not null,
	created_at timestamp default now(), -- column with the current timestamp as a default value
	updated_at timestamp default null,
	foreign key (user_id) references users(id) -- foreign key
);
```

```sql
create table categories (
	id bigserial primary key,
	title varchar(255) not null unique
);
```

```sql
create table post_category (
	post_id bigint,
	category_id bigint,
	primary key (post_id, category_id) -- Composite primary key (primary key on more than one column(s))
);
```

```sql
create table comments (
	id bigserial primary key,
	parent_id bigint default null,
	user_id bigint not null,
	post_id bigint not null,
	body varchar(500) not null,
	foreign key(user_id) references users(id),
	foreign key(post_id) references posts(id),
	foreign key(parent_id) references comments(id) -- foreign key referencing itself
);
```

### QUERIES

- Top 3 salaries:

```sql
select * from (select salary from employees group by salary order by salary desc) as salaries limit 3;
```
