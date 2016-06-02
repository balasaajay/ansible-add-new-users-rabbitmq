# ansible-add-new-users-rabbitmq
Run this playbook to add new users to rabbitmq using APIs

Make sure rabbitmq's management port is open (default is 15672).

## Command to run the playbook

```ansible-playbook add_user_rabbitmq.yml --extra-vars "vhost_name=sensu user_new=sensu password_new=sensu123 rabbitmq_url=http://localhost:15762"```

In this command, assign values as appropriate to vhost_name, user_new, password_new,rabbitmq_url variables.

## What this does?

1) Verifies whether requested vhost exists or not. If requested vhost exists, playbook exits and displays ERROR.

2) Verifies whether requested user exists or not. If requested user exists, playbook exits and displays ERROR.

3) Creates vhost and verifies whether it is created sucessfully or not.

4) Creates user with requested password and assigns '(None)' tag to it. The tag can be modified by changing it in playbbok.

5) Sets user permissions and verifies them by getting the permissions

