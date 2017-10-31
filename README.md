TASK DATE: 29.10.2017 - FINISHED: 29.10.2017

TASK SHORT DESCRIPTION: 1174 (redirect to login page)

GITHUB REPOSITORY CODE: hotfix/task-1174-redirect-to-login-page

ORIGINAL WORK: https://github.com/BusinessBecause/network-site/tree/hotfix/task-1174-redirect-to-login-page


CHANGES
 
	IN FILES: 
	
		\network-site\addons\default\modules\network_settings\controllers\errors.php
		
			CHANGED CODE: 
			
				FROM: 
				
					public function no_permission()
					{
						$this->template
									->build('errors/no_permission', $this->data);
					}
					
				TO:
			
					public function no_permission()
					{
						if (($this->ion_auth->logged_in())) {
							$this->template
										->build('errors/no_permission', $this->data);
						}
						else {
							redirect('users/login');
						}
					}
