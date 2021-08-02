# Basic Info
### Ihor Novikov

# Contact info
E-mail: [novikov8118@gmail.com](novikov8118@gmail.com)  
Phone number: +38(067)363-14-57  
Social networks: [Facebook](https://www.facebook.com/igor.novikov.8118 "Facebook")

# Summary
My goal is to find a company where I can grow my career and develop new professional skills. It’s amazing to learn something new.

**Personal qualities:**
- Motivation to grow and learn new programming languages and technologies
- Good communication skills
- Able to solve difficult problems and extremely good at planning
- Strong analytical skills and good grasp about managing a team

# Skills
- **Technologies and frameworks:** HTML, CSS, Javascript, ReactJS, NodeJS 
- **Source Control:** GitHub
- **OS:** Ubuntu, Windows

# Code examples 
```import React, { useState } from 'react'
import { access } from './access'
import styles from './authForm.module.css'
import NavBar from '../NavBar/NavBar'


const AuthForm = ({ allUs, allPass, firstName, lastName, email }) => {

	const [username, setUsername] = useState('');
	const [password, setPassword] = useState('');
	const [isLoading, setIsLoading] = useState(false);
	const [isLoggedIn, setIsLoggedIn] = useState(false);
	const [error, setError] = useState('');
	const [form, setForm] = useState(styles.formPassive);

	const onSubmit = async e => {
		e.preventDefault();
		setIsLoading(true);
		setError('');

		try {
			await access(username, password, allUs, allPass);
			setIsLoggedIn(true);
			setError('');
			setPassword('');
		} catch (error) {
			setError('Incorrect username or password');
		}
		setIsLoading(false);
	};

	const onClick = () => {
		setError('');
		setForm(styles.formActive);
		setUsername('');
		setPassword('');
	}


	function InvalidMsg(e) {
		if ((username === '') && (password === '')) {
			setError('Please enter username and password');
		}
		else if (username === '') {
			setError('Please enter username');
		}
		else {
			setError('Please enter password');
		}
	}

	return (
		<>
			{isLoggedIn ? ( 	
				<div>
					<div className={styles.userGreeting}>
						<div>Welcome</div>
						<div>{username}!</div>
						<button onClick={() => setIsLoggedIn(false)}>Log Out</button>  
					</div>


				</div>) : (
					<form className={form} onSubmit={onSubmit}>
						<p className={styles.formGreeting}>Login to your account</p>
						<div>
							<button className={styles.closeForm} onClick={() => setForm(styles.formPassive)}>&times;</button>

							<input className={styles.inputName}
								type="text"
								placeholder="username"
								value={username}
								onChange={(e) => { setUsername(e.currentTarget.value) }}
								onInvalid={InvalidMsg}
								required
							/> </div>
						<div>
							<input className={styles.inputPass}
								type="password"
								placeholder="password"
								value={password}
								onChange={(e) => setPassword(e.currentTarget.value)}
								onInvalid={InvalidMsg}
								required
							/> </div>
						<button
							className={styles.submit}
							type="submit"
						>
							{isLoading ? 'Logging In ' : 'Log In'} 
						</button>
						{error && <p className={styles.error}>{error}</p>}
					</form>
				)}
			<NavBar isLoggedIn={isLoggedIn} username={username} onClick={onClick} firstName={firstName} lastName={lastName} email={email} />

		</>
	)
};

export default AuthForm;
```
# Experience 
Took part in the creation of an application that provides information about the equipment condition and current works in RNPP.

# Education
Master of Arts(M.A.) degree in Atomic energy  
2006 Sevastopol national University of Nuclear Energy and Industry (SNUNEI)


# English 
**Upper-Intermediate(B2)** [Tracktest certificate](https://app.tracktest.eu/index.php?share=5dfc9f37867eb4b216575abe6492a5bc6cf1612cf9f0db315484db3f8124)  
I can understand the main ideas of complex text on both concrete and abstract topics, including technical discussions in my field of specialisation. I can produce clear, detailed text on a wide range of subjects. 

