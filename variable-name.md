# AI Coding Rules: Clean, Readable, Maintainable Code

Follow these rules for every piece of code you write or modify.

## 1. Variable Naming

Always use clear, descriptive, meaningful variable names.

Never use unnecessarily shortened variable names.

### Bad

```python
n = 10
u = user
d = data
i = 0
x = request.GET.get("x")
usr = User.objects.get(id=user_id)
amt = 500
qty = 10
res = calculate_total()
```

### Good

```python
number = 10
user = user
data = data
index = 0
search_query = request.GET.get("search_query")
user = User.objects.get(id=user_id)
amount = 500
quantity = 10
result = calculate_total()
```

## 2. Never Use Single-Letter Variables Unless Mathematically Necessary

Avoid:

```python
n
i
j
x
y
z
d
t
v
q
r
```

Use descriptive names:

```python
number
index
row_index
column_index
coordinate_x
coordinate_y
date
timestamp
value
search_query
response
```

The only acceptable exceptions are short mathematical or universally understood contexts where the meaning is obvious.

Example:

```python
for index in range(10):
    ...
```

is preferred over:

```python
for i in range(10):
    ...
```

## 3. Use Full Words

Do not abbreviate variable names unnecessarily.

### Bad

```python
usr
pwd
addr
qty
amt
msg
cfg
resp
req
obj
cnt
idx
val
num
desc
info
temp
```

### Good

```python
user
password
address
quantity
amount
message
configuration
response
request
object
count
index
value
number
description
information
temporary_value
```

Common technical abbreviations that are universally understood may be used when appropriate, such as:

```python
id
url
api
http
https
html
css
sql
json
xml
uuid
ip
```

Do not invent abbreviations.

## 4. Variable Names Must Explain Their Purpose

A variable should be understandable without reading the surrounding implementation.

### Bad

```python
data = get_data()
result = process(data)
```

### Good

```python
fabric_records = get_fabric_records()
processed_fabric_records = process_fabric_records(fabric_records)
```

Use domain-specific names when the domain is known.

For example:

```python
marker_length
cutting_quantity
fabric_quantity
job_number
style_name
buyer_name
order_quantity
shipment_date
production_date
```

instead of:

```python
ml
cq
fq
jn
sn
bn
oq
sd
pd
```

## 5. Function Names Must Be Descriptive

Function names must clearly describe what the function does.

### Bad

```python
def process():
    ...

def get_data():
    ...

def handle():
    ...

def do_task():
    ...
```

### Good

```python
def calculate_total_order_quantity():
    ...

def get_fabric_balance_records():
    ...

def validate_cutting_record():
    ...

def generate_production_report():
    ...
```

Prefer verbs for functions:

```python
get_
create_
update_
delete_
calculate_
validate_
check_
generate_
process_
parse_
build_
convert_
export_
import_
```

## 6. Class Names Must Be Descriptive

Use clear PascalCase names.

### Bad

```python
class Data:
    ...

class Manager:
    ...

class Handler:
    ...
```

### Good

```python
class FabricBalanceRecord:
    ...

class ProductionReportManager:
    ...

class CuttingDataImportHandler:
    ...
```

Avoid generic class names when a more specific name is possible.

## 7. Boolean Variables Must Read Like Questions

Boolean variables should clearly communicate that they contain `True` or `False`.

### Bad

```python
active = True
check = False
status = True
permission = False
```

### Good

```python
is_active = True
is_valid = False
is_completed = True
has_permission = False
can_edit = True
should_process = False
```

Use prefixes such as:

```text
is_
has_
can_
should_
was_
```

## 8. Constants

Use `UPPER_SNAKE_CASE` for constants.

### Good

```python
MAX_RETRY_COUNT = 3
DEFAULT_PAGE_SIZE = 50
MAX_FILE_SIZE_MB = 10
DEFAULT_TIMEOUT_SECONDS = 30
```

Do not use:

```python
x = 3
limit = 50
timeout = 30
```

when the value represents a system-wide constant.

## 9. Avoid Generic Names

Avoid meaningless names such as:

```python
data
temp
thing
stuff
item
obj
value
result
response
output
```

unless the meaning is genuinely generic.

Instead of:

```python
data = get_data()
```

prefer:

```python
fabric_records = get_fabric_records()
```

Instead of:

```python
result = calculate(data)
```

prefer:

```python
total_fabric_quantity = calculate_total_fabric_quantity(fabric_records)
```

## 10. Loop Variables

Use descriptive loop variables whenever the collection contains meaningful domain objects.

### Bad

```python
for x in records:
    print(x.job_no)
```

### Good

```python
for fabric_record in fabric_records:
    print(fabric_record.job_no)
```

For nested loops:

### Bad

```python
for i in data:
    for j in i:
        ...
```

### Good

```python
for production_record in production_records:
    for cutting_record in production_record.cutting_records:
        ...
```

## 11. Dictionary and List Variables

Name collections using plural nouns.

### Good

```python
users
fabric_records
cutting_records
job_numbers
style_names
marker_lengths
production_reports
```

Name a single object using a singular noun.

```python
user
fabric_record
cutting_record
job_number
style_name
marker_length
production_report
```

Never mix them unnecessarily.

### Bad

```python
user_list
data_list
record_data
```

### Good

```python
users
records
fabric_records
```

## 12. Do Not Reuse Variables for Different Meanings

Never do this:

```python
data = get_users()
data = process_orders(data)
data = calculate_total(data)
```

Use meaningful names:

```python
users = get_users()
processed_orders = process_orders(users)
total_order_quantity = calculate_total(processed_orders)
```

Each variable should have one clear responsibility.

## 13. Do Not Shadow Important Variables

Avoid:

```python
user = get_user()

for user in users:
    ...
```

Prefer:

```python
current_user = get_user()

for user in users:
    ...
```

Or:

```python
selected_user = get_user()

for user in users:
    ...
```

## 14. Function Arguments Must Be Descriptive

### Bad

```python
def calculate(a, b, c):
    ...
```

### Good

```python
def calculate_total_cost(
    unit_price,
    quantity,
    discount_percentage,
):
    ...
```

The function should be understandable from its signature.

## 15. Do Not Use Comments to Compensate for Bad Naming

### Bad

```python
# Get the number of ordered pieces
n = order.quantity
```

### Good

```python
order_quantity = order.quantity
```

Good variable names reduce the need for comments.

## 16. Preserve Existing Naming Conventions

Before adding code to an existing project:

1. Inspect the existing code.
2. Identify the project's naming conventions.
3. Follow the project's established conventions.
4. Do not randomly rename unrelated existing variables.
5. Do not introduce a new naming style without a reason.

Consistency is more important than personal preference.

## 17. Django Naming

Follow Django conventions.

### Models

Use singular PascalCase:

```python
class FabricBalanceRecord(models.Model):
    ...
```

### Fields

Use descriptive `snake_case`:

```python
job_number
style_name
order_quantity
shipment_date
created_at
updated_at
```

### QuerySets

Use plural names:

```python
fabric_records = FabricBalanceRecord.objects.all()
cutting_records = CuttingRow.objects.filter(...)
```

### Single Objects

Use singular names:

```python
fabric_record = FabricBalanceRecord.objects.get(...)
cutting_record = CuttingRow.objects.get(...)
```

### Views

Use descriptive names:

```python
def fabric_balance_list(request):
    ...

def cutting_analysis(request):
    ...

def import_fabric_records(request):
    ...
```

Avoid:

```python
def view1(request):
def test(request):
def data(request):
def process(request):
```

## 18. API Naming

Use descriptive names for API data.

### Bad

```json
{
    "n": 100,
    "q": 50,
    "d": "2026-10-04"
}
```

### Good

```json
{
    "order_quantity": 100,
    "cutting_quantity": 50,
    "production_date": "2026-10-04"
}
```

Use the same naming consistently between:

```text
Database
Django model
Serializer
API
Frontend
JavaScript
Documentation
```

## 19. JavaScript Naming

Use descriptive `camelCase`.

### Bad

```javascript
const d = response.data;
const u = currentUser;
const btn = document.querySelector("#btn");
```

### Good

```javascript
const responseData = response.data;
const currentUser = currentUser;
const submitButton = document.querySelector("#submit-button");
```

Use:

```javascript
const selectedJobNumber = ...
const fabricRecords = ...
const isLoading = ...
const hasPermission = ...
```

## 20. Python Naming

Use `snake_case`.

```python
job_number
fabric_records
order_quantity
total_marker_length
is_completed
```

Classes use `PascalCase`:

```python
FabricBalanceRecord
ProductionReport
CuttingAnalysisService
```

Constants use `UPPER_SNAKE_CASE`:

```python
MAX_RETRY_COUNT
DEFAULT_PAGE_SIZE
```

## 21. Do Not Over-Shorten Names for Line Length

Do not turn:

```python
fabric_balance_records
```

into:

```python
fbr
```

just because the line becomes long.

Instead, restructure the code:

```python
fabric_balance_records = (
    FabricBalanceRecord.objects
    .filter(...)
    .select_related(...)
)
```

Readable structure is better than abbreviated names.

## 22. Use Domain Language

Use the terminology that the business actually uses.

For textile/RMG systems:

```python
buyer
style
job_number
order_quantity
fabric_type
fabric_quantity
marker_number
marker_length
cut_number
cutting_quantity
batch_number
supervisor
production_date
shipment_date
```

Do not replace meaningful business terms with generic technical names.

## 23. No Random Naming

Never generate names like:

```python
data1
data2
data3
temp1
temp2
result1
result2
new_data
new_result
final_data
final_result
```

If multiple values exist, distinguish them by meaning:

```python
raw_fabric_data
validated_fabric_data
processed_fabric_data
export_ready_fabric_data
```

## 24. Do Not Add Unnecessary Complexity

Clean naming does not mean creating excessively long names.

Bad:

```python
the_currently_selected_fabric_balance_record_from_database
```

Good:

```python
selected_fabric_record
```

The goal is **maximum clarity with minimum unnecessary length**.

## 25. Before Writing Code

Before generating code, determine:

* What does this variable represent?
* Is it a single object or a collection?
* What is its domain meaning?
* Is it a boolean?
* Is it a constant?
* What unit does it represent?
* What does the function actually do?
* Does the existing project already have a naming convention?

Then choose the name.

## 26. Final Code Quality Requirement

Generated code must be:

* Readable
* Explicit
* Consistent
* Descriptive
* Maintainable
* Self-explanatory
* Consistent with the existing project
* Free from unnecessary abbreviations
* Free from meaningless variable names
* Free from single-letter variables unless genuinely justified

### Core Rule

**Never optimize variable names for typing speed. Optimize them for human understanding.**

Prefer:

```python
order_quantity
```

over:

```python
oq
```

Prefer:

```python
fabric_records
```

over:

```python
fr
```

Prefer:

```python
production_date
```

over:

```python
pd
```

Prefer:

```python
search_query
```

over:

```python
q
```

Prefer:

```python
total_cutting_quantity
```

over:

```python
tcq
```

Code should be understandable months later by a developer who did not write it.
