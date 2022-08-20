#session 10
(1401.05.23)

## React
### Conditional Rendering
 - you can render only some of components, depending on the state of your application.
 -  Use JavaScript operators like if or the conditional operator to create elements representing the current state, and let React update the UI to match them.
 
 `
	 function Greeting(props) {
	  const isLoggedIn = props.isLoggedIn;
	  if (isLoggedIn) {
	 	 return <UserGreeting />;
	  } 
	  return <GuestGreeting />;
	  } 
  `
  
 #### Element Variables 
 - You can use variables to store elements.
 - his can help you conditionally render a part of the component while the rest of the output doesn’t change.
 
 `
 
	   render() {
	    const isLoggedIn = this.state.isLoggedIn;
	    let button; 
	    if (isLoggedIn) {     
	     button = <LogoutButton onClick={this.handleLogoutClick} />; 
	     } else {
	     button = <LoginButton onClick={this.handleLoginClick} />;
	     }
	     
	    return (
	      <div>
		<Greeting isLoggedIn={isLoggedIn} />  
		{button}     
	      </div>
	    );
	  }
  
  `
  - There are a few ways to inline conditions in JSX:
  
  #### Inline If with Logical && Operator
  
  if the condition is true, the element right after && will appear in the output. If it is false, React will ignore and skip it.
  
  `
	  function Mailbox(props) {
	  const unreadMessages = props.unreadMessages;
	  return (
	    <div>
	      <h1>Hello!</h1>
	      {unreadMessages.length > 0 && 
	       <h2>You have {unreadMessages.length} unread messages.</h2>
	      }    
	    </div>
	  );
	}
	
  ` 
  Note that returning a falsy expression will still cause the element after && to be skipped but will return the falsy expression.
  
  
  #### Inline If-Else with Conditional Operator
  
  - conditional `operator condition ? true : false`.
  `
	render() {
	  const isLoggedIn = this.state.isLoggedIn;
	  return (
	    <div>
	      {isLoggedIn ? <LogoutButton onClick={this.handleLogoutClick} />
		          : <LoginButton onClick={this.handleLoginClick} /> 
              }
	    </div> );
	}
   `
   
   #### Preventing Component from Rendering 
   
   In rare cases you might want a component to hide itself even though it was rendered by another component. To do this return null instead of its render output.
   
   `
	function WarningBanner(props) {
	  if (!props.warn) {
	      return null;  
	   }
	   
	  return (
	    <div className="warning">
	      Warning!
	    </div>
	  );
	}
    `
