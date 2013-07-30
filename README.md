MailChimp API
=============

Super-simple, minimum abstraction MailChimp API v2 wrapper, in PHP.

I hate complex wrappers. This lets you get from the MailChimp API docs to the code as directly as possible.

Requires curl and a pulse.

Examples
--------

List lists (lists/list method)

	$MailChimp = new MailChimp('abc123abc123abc123abc123abc123-us1');
	print_r($MailChimp->call('lists/list'));

Subscribe someone to a list

	$MailChimp = new MailChimp('abc123abc123abc123abc123abc123-us1');
	$result = $MailChimp->call('lists/subscribe', array(
					'id'                => $list_id,
					'email'             => array('email'=>'foo@example.com'),
					'merge_vars'        => array('FNAME'=>'Bob', 'LNAME'=>'Monkhouse'),
					'double_optin'      => 'false',
					'update_existing'   => 'true',
					'replace_interests' => 'false',
					'send_welcome'      => 'false',
				));
	print_r($result);