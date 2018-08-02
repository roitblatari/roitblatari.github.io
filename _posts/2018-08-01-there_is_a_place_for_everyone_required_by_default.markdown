---
layout: post
title:      " There is a place for everyone  'required by default'"
date:       2018-08-01 13:25:07 -0400
permalink:  there_is_a_place_for_everyone_required_by_default
---



As the trees are get filled with fresh green leaves and the warm winds of summer settle in, I remind myself of my first experience in overnight summer camp. Brave enough to venture across the border on my own, but hesitant to spark new friendships, I was determined to make it the best summer. Fast forward about 20 years, and here I am, creating an app to “Get the Job Done”. This platforms allows employers to post jobs that need to be fulfilled, so that employees can log on and select the jobs which they would like to accomplish, subsequently marking the job as done by removing it from the index page.
Trying to connect three that don’t know each other: Employer, Employee and Job, felt like making new friends and connecting to new people, but this time it’s behind the screen, creating a network so that Employer, Employee and Job can all be connected. 
Being that Rails 5 makes belongs_to association required by default, my challenge now was to create a job without it having to be associated to an employee. 

```
class Employee < ApplicationRecord
  has_many :jobs
  has_many :employers, through: :jobs
end
​
class Employer < ApplicationRecord
  has_many :jobs
  has_many :employees, through: :jobs
end

class Job < ApplicationRecord
  belongs_to :employee
  belongs_to :employer
end
​
> job = Job.create(title: 'Hi')
=> <Job id: nil, title: "Hi", employee_id: nil,employer_id: "1", created_at: nil, updated_at: nil>
​
job.errors.full_messages.to_sentence
=> "Employee must exist"

```


Some googling taught me how to achieve this behavior, by opting out of this default behavior in Rails  5


We can pass “optional: true” to the “belongs_to” association which would remove this validation check. 
```
class Job < ApplicationRecord
  belongs_to :employee, optional: true
end

job = Job.create(title: 'Hi')
=> <Job id: 2, title: "Hi", employee_id: nil, employer_id: "1">
```



