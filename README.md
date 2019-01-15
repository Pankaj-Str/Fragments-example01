Introduction to Fragments | Android
A Fragment is a piece of an activity which enable more modular activity design. A fragment encapsulates functionality so that it is easier to reuse within activities and layouts.
Android devices exists in a variety of screen sizes and densities. Fragments simplify the reuse of components in different layouts and their logic. You can build single-pane layouts for handsets (phones) and multi-pane layouts for tablets. You can also use fragments also to support different layout for landscape and portrait orientation on a smartphone.


onAttach() : The fragment instance is associated with an activity instance.The fragment and the activity is not fully initialized. Typically you get in this method a reference to the activity which uses the fragment for further initialization work.
onCreate() : The system calls this method when creating the fragment. You should initialize essential components of the fragment that you want to retain when the fragment is paused or stopped, then resumed.
onCreateView() : The system calls this callback when it’s time for the fragment to draw its user interface for the first time. To draw a UI for your fragment, you must return a View component from this method that is the root of your fragment’s layout. You can return null if the fragment does not provide a UI.
onActivityCreated() : The onActivityCreated() is called after the onCreateView() method when the host activity is created. Activity and fragment instance have been created as well as the view hierarchy of the activity. At this point, view can be accessed with the findViewById() method. example. In this method you can instantiate objects which require a Context object
onStart() : The onStart() method is called once the fragment gets visible.
onResume() : Fragment becomes active.
onPause() : The system calls this method as the first indication that the user is leaving the fragment. This is usually where you should commit any changes that should be persisted beyond the current user session.
onStop() : Fragment going to be stopped by calling onStop()
onDestroyView() : Fragment view will destroy after call this method
onDestroy() :called to do final clean up of the fragment’s state but Not guaranteed to be called by the Android platform.
Types of Fragments

Single frame fragments : Single frame fragments are using for hand hold devices like mobiles, here we can show only one fragment as a view.
List fragments : fragments having special list view is called as list fragment
Fragments transaction : Using with fragment transaction. we can move one fragment to another fragment.
Handling the Fragment Lifecycle

A Fragment exist in three states :

Resumed : The fragment is visible in the running activity.
Paused : Another activity is in the foreground and has focus, but the activity in which this fragment lives is still visible (the foreground activity is partially transparent or doesn’t cover the entire screen).
Stopped : The fragment is not visible. Either the host activity has been stopped or the fragment has been removed from the activity but added to the back stack. A stopped fragment is still alive (all state and member information is retained by the system). However, it is no longer visible to the user and will be killed if the activity is killed.


package com.saket.geeksforgeeks.demo; 
  
import android.app.Fragment; 
import android.os.Bundle; 
import android.view.LayoutInflater; 
import android.view.View; 
import android.view.ViewGroup; 
import android.widget.TextView; 
  
public class DetailFragment extends Fragment  
{ 
      
    @Override
    public View onCreateView(LayoutInflater inflater, ViewGroup container, 
                            Bundle savedInstanceState)  
        { 
              
            View view = inflater.inflate(R.layout.fragment_rssitem_detail, 
                container, false); 
                  
            return view; 
        } 
  
    public void setText(String text)  
    { 
        TextView view = (TextView) getView().findViewById(R.id.detailsText); 
        view.setText(text); 
    } 
} 
