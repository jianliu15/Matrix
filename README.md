## LBS based Android App for Smart Driving

### Project Description
- Matrix is an Android Project which provides a general platform for drivers to share traffic condition events. 
- Drivers are able to register their accounts and able to login. Driver can upload events, watch events, check details and give comments on Google Map interface.
- Matrix uses cutting-edge framework Firebase to establish flexible and maintainable backend service group. Uses Toolbar, ViewPager and NavigationView combination to build user-friendly UI framework. Integrated Google Map to allow users checking instant events at their convenience. 

### Project Structure

- 1. OnBoardingActivity

	The screen where allows user to login and register as folows:

<img src="/images/Login.PNG">
<img src="/images/Register.PNG" width="100x">

<table>
    <tr>
        <td>Part</td> 
        <td>Files Related</td> 
		<td>Description</td> 
    </tr>
    <tr>
        <td rowspan="2">OnBoardingActivity</td>    
        <td>OnBoardingActivity.java</td>  
		<td>The screen where allows user to login and register</td>  
    </tr>
    <tr>
        <td>res/layout/activity_on_boarding.xml</td>  
		<td>Layout file</td>  
    </tr>
	<tr>
		<td>Viewpager</td> 
        <td>OnBoardingActivity.java</td>  
		<td>It uses the OnBoardingPageAdapter to load LoginFragment and RegisterFragment</td>  
    </tr>
	<tr>
		<td>OnBoardingBaseFragment</td> 
        <td>OnBoardingBaseFragment.java</td>  
		<td>Base fragment of the Login and RegisterFragment which has the shared logic setup</td>  
    </tr>
	<tr>
		<td rowspan="2">LoginFragment</td> 
        <td>LoginFragment.java</td>  
		<td>Extends OnBoardingBaseFragmentBase and defines the login related business logic</td>  
    </tr>
	<tr>
        <td>res/layout/fragment_login.xml</td>  
		<td>LoginFragment’s layout file</td>  
    </tr>
		<tr>
		<td rowspan="2">RegisterFragment</td> 
        <td>RegisterFragment.java</td>  
		<td>Extends OnBoardingBaseFragmentBase and defines the register related business logic</td>  
    </tr>
	<tr>
        <td>res/layout/fragment_login.xml</td>  
		<td>RegisterFragment’s layout file</td>
    </tr>
</table>


- 2. ControlPanelActivity

	Control Panel is the container of everything inside, including MainFragment. Other than that Fragments, ControlPanel also contains ToolBar and Navigation View

<img src="/images/ToolBar.PNG" width="100x">
<img src="/images/NavigationView.PNG" width="100x">


<table>
    <tr>
        <td>Part</td> 
        <td>Files Related</td> 
		<td>Description</td> 
    </tr>
    <tr>
        <td rowspan="2">Toolbar</td>    
        <td>ControlPanel.java</td>  
		<td>ControlPanel includes Toolbar</td>  
    </tr>
    <tr>
        <td>res/layout/activity_control_panel.xml</td>  
		<td>ControlPanel includes Toolbar</td>  
    </tr>
	<tr>
		<td rowspan="4">NavigationView</td> 
        <td>ControlPanel.java</td>  
		<td>ControlPanel includes NavigationView</td>  
    </tr>
	<tr>
        <td>res/layout/activity_control_panel.xml</td>  
		<td>ControlPanel includes NavigationView</td>  
    </tr>
        <td>res/layout/nav_header.xml</td>  
		<td>The layout of navigationview header, at the top</td>  
    </tr>
	<tr>
        <td>res/menu/drawer_view.xml</td>  
		<td>The menu item below navigationvie header, includes settings & homes</td>
    </tr>
</table>

- 3. MainFragment

	Main Fragment is the main user interface, it includes several features：
	- 3.1. The main feature, it shows Google Map and event on screen:
	
<table>
    <tr>
        <td>Part</td> 
        <td>Files Related</td> 
		<td>Description</td> 
    </tr>
    <tr>
        <td rowspan="4">MainFragment (Main Feature)</td>    
        <td>ControlPanel.java</td>  
		<td>ControlPanel contains MainFragment</td>  
    </tr>
    <tr>
        <td>MainFragment.java</td>  
		<td>Main Fragment logic java file</td>  
    </tr>
	<tr>
        <td>res/layout/fragment_main.xml</td>  
		<td>Main Fragment main UI container</td>  
    </tr>
	<tr>
        <td>res/raw/style_json</td>  
		<td>Styling Google map</td>  
    </tr>
</table>
	
	- 3.2. Open ReportDialog and take the dialog’s callback to upload Event to Firebase (Click button on right-bottom corner of picture above)
	
<table>
    <tr>
        <td>Part</td> 
        <td>Files Related</td> 
		<td>Functions Related</td> 
		<td>Description</td> 
    </tr>
    <tr>
        <td rowspan="4">MainFragment (Upload Event)</td>    
        <td rowspan="4">MainFragment.java</td>  
		<td>showdialog</td> 
		<td>Open the ReportDialog</td>  		
    </tr>
    <tr>
        <td>askSpeechInput</td>  
		<td>Open the system speech recognition</td>  
    </tr>
	<tr>
        <td>startCamer</td>  
		<td>Take the callback from ReportDialog and open the camera</td>  
    </tr>
	<tr>
        <td>onSubmit and uploadImage</td>  
		<td>Take the callback and data from ReportDialog and uploadEvent</td>  
    </tr>
	<tr>
        <td> interface DialogCallBack {
				void onSubmit(String editString, String event_type);
				void startCamera();
			}
		</td>  
		<td>MainFragment’s callback listener from ReportDialog</td>  
    </tr>
</table>	
	