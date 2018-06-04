FOR PRIVACY AND CODE PROTECTING REASONS THIS IS A SIMPLIFIED VERSION OF CHANGES AND NEW FEATURES

TASK DATE: 29.10.2017 - FINISHED: 29.10.2017

TASK LEVEL: (EASY)  

TASK SHORT DESCRIPTION: 1174 (redirect to login page)

GITHUB REPOSITORY CODE: hotfix/task-1174-redirect-to-login-page

CHANGES
 
	IN FILES: 
	
		errors.php
		
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
