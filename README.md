# SSNS
**S**imple **S**tochastic and **N**onlinear **S**imulator, a web app

* interface with [Bootstrap](https://getbootstrap.com/) so that app is easy to use from both mobile and desktop browsers
* plotting relies on the [flot library](https://www.flotcharts.org/), or, for heatmaps, the native HTML canvas element
* web typesetting is done using the [KaTeX library](https://www.katex.org/)
* dependencies include:

### Classes, Hierarchies, etc.
The following classes, which are roughly listed from "largest" (i.e., "outermost") to "smallest," are not part of large class hierarchies, and are often present only as a single instance:

* <samp>SSNS</samp> = **S**imple **S**tochastic and **N**onlinear **S**imulator
* <samp>UserInterface</samp>
* <samp>PlottingMachinery</samp>
* <samp>RunState</samp>
* <samp>UINI</samp> = **U**ser **I**nterface **N**umerical **I**nput
* <samp>HelpViewerNode</samp>
* <samp>HelpViewer</samp>

A few notes:

* <samp>SSNS</samp>, as the name suggests, is the JavaScript class that encompasses all app logic.  It is instantiated between a pair of <samp>script</samp> tags at the very end of [<samp>SSNS.html</samp>](SSNS.html)
* <samp>HelpViewer</samp> is a modal-lightbox-based network of help pages, each corresponding to a <samp>HelpViewerNode</samp>; see the [Help Viewer](#help-viewer) section for details and a "sitemap" of node pages.

### Input/Output

Input to the app is done only via the user interface.  On loading of the page, the app shows the default system type and plots its trajectory.  At that point, the trajectory consists of only a single time point &mdash; the default initial condition &mdash; so pressing "play" will do nothing!  More trajectory must be generated by pressing "record."  Once there are two or more time steps, record/backward-play/pause/forward-play, as well as other trajectory navigation commands, become possible.  (This behavior may be confusing if the user expects something like a music player, while the app is more like an audio recorder.)

In addition to buttons, checkboxes, etc., the app has many text input fields for passing in numbers.  Each input field is presented in a "block," with a symbol/word label on a blue or green background on the left.  Some blocks also have a dedicated "apply" button or related controls to the right.  Under the hood, each input field uses an HTML <samp>input</samp> element with <samp>type="number"</samp>.  Note that the presence of small increment/decrement arrows, the popup of numeric keyboards, etc. will all depend on choice of browser and mobile vs. desktop.

In a "layer" one below the raw input fields, each HTML input is managed by an instance of the <samp>UINI</samp> (**U**ser **I**nterface **N**umerical **I**nput) class.  The goals of this setup are:

* take full advantage of HTML  <samp>input</samp> <samp>type="number"</samp>
* 

Outputting trajectory data is not implemented, nor planned, but would be very doable... either saving to disk through the browser or just opening a new tab with text data.  And screenshots are always possible, of course 😀.  Similarly, reading saved trajectory in from disk is neither implemented nor planned.

### Help Viewer
blah blah

	    HV_HOME
		HV_USING
		    HV_PLOT_AREA
		    HV_MAIN_PANEL
		    HV_C_CONTINUOUS_CMDS
		    HV_PRMS_DROPDOWN
		    HV_CTRL_DROPDOWN
			HV_C_ONE_STEP_CMDS
			HV_C_PLOT_TYPES
			HV_C_T_DT_JUMP
			HV_C_DELAY_WINDOW
			HV_C_T_0_MAX_STOP
			HV_C_RNG_RECR_TRAJ
			HV_C_SP_ENSEMBLE
			HV_C_RELOAD_CMDS
		    HV_SYS_DROPDOWN
		    HV_HELP_VIEWER
		HV_COMPUTATION
		    HV_CODE_ORGANIZATION
		    HV_CODE_DEPENDENCIES
		    HV_CODE_LIMITATIONS
		    HV_CODE_IO
		    HV_ERRORS
			HV_E_T_MAX_REACHED
		HV_CONCEPTS
		    HV_ENSEMBLES
		    HV_MARKOV_ONE_STEP
		    HV_SPIN_SYSTEMS
		    HV_PHASE_TRANSITIONS
		    HV_SA_SP
			HV_ST_MN
			    HV_P_SP_MN_mu
			    HV_P_SP_MN_s
			    HV_P_SP_MN_N
			    HV_P_SP_MN_x_0
		    HV_SA_SM
			HV_ST_IS
			    HV_P_SM_IS_T
			    HV_P_SM_IS_h
			    HV_P_SM_IS_N
			HV_ST_XY
			    HV_P_SM_XY_T
			    HV_P_SM_XY_h
			    HV_P_SM_XY_N
		    HV_SA_ND
			HV_ST_LM
			    HV_P_ND_LM_r
			    HV_P_ND_LM_x_0
			HV_ST_GM
			    HV_P_ND_GM_x_0
			    HV_P_ND_GM_y_0
		    HV_SA_FD
			HV_ST_EU
			HV_ST_PF
		    HV_MINI_SCENARIOS
