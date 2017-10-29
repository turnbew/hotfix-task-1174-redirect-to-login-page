TASK DATE: 29.10.2017 - Finished: 29.10.2017

TASK SHORT DESCRIPTION: 1174 (redirect to login page)

GITHUB REPOSITORY CODE: hotfix/task-1174-redirect-to-login-page

ORIGINAL WORK: https://github.com/BusinessBecause/network-site/tree/hotfix/task-1174-redirect-to-login-page


CHANGES
 
	IN FILES: 
	
		\network-site\addons\default\modules\network_settings\controllers\errors.php
		
			CHANGED CODE: 
			
				FROM: 
				
					$this->template
							->build('errors/no_permission', $this->data);
					
				TO:
			
					//in hotfix/task-1174-redirect-to-login-page was asked to redirect this site to login site
					redirect('users/login');
					
					//$this->template
					//    ->build('errors/no_permission', $this->data);
