<u>Module objectives</u>
1. explain what a penetration test is
2. identify the rules of engagement and how to perform a pen test
3. define vulnerability scanning
4. describe different cybersecurity resources

- **Penetration testing** - attempts to exploit vulnerabilities just as a threat actor would, with the goal of uncovering new vulnerabilities, providing a clearer picture of their nature, and determining how they could be used against the org
	- *Planning is critical* - lack of planning can result in a flawed test that tries to do too much or too little. Can also result in *creep*, or an expansion beyond the initial set of the test's limitations
	- can detect a different kind of vulnerabilities than a network scan. Scans usually only detect surface problems due to being entirely automated and providing limited verification. Pen tests can find much deeper vulnerabilities using manual techniques
	- *Who performs the test?* 
		- **Internal Security Personnel** - <u>advantages</u> include little to no additional cost, tests can be performed very quickly, and can also be used to enhance training of employees and raise security awareness. Also several <u>disadvantages</u>: inside knowledge prevents true simulation of attacker, lack of expertise may limit the ability to perform a comprehensive test, or they may be reluctant to reveal a vulnerability that they or a fellow employee were charged with protecting
		- **External Pen Tester Consultant** - <u>Advantages</u>: higher technical and business expertise, higher credentials and certifications, more pen testing experience to look for vulnerabilities, and a deeper focus on the task of testing.
			- *Black Box* - testers have no knowledge of network, emulates exactly what an attacker would do and see, though if they can't successfully penetrate then no test can occur
			- *Gray Box* - testers are given limited knowledge of the network and some elevated privileges. This lets them more efficiently assess security, but does not completely simulate the position an attacker would be starting from
			- *White Box* - testers are given full knowledge of network and source code of applications. This allows them to focus directly on systems to test for penetration, but does not provide a full picture of the network's vulnerabilities
		- 