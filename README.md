# Pull-To-Refresh-ListView
PullToRefresh with progress bar. Simple callback!

# Install

Add to your gradle dependencies:

	compile 'me.aflak.libraries:pulltorefresh:1.0'
	
# XML

    <me.aflak.pulltorefresh.PullToRefresh
      android:id="@+id/pull_to_refresh"
      android:layout_width="match_parent"
      android:layout_height="match_parent">
      <ListView
          android:id="@+id/list"
          android:layout_width="match_parent"
          android:layout_height="match_parent"/>
    </me.aflak.pulltorefresh.PullToRefresh>
    
# JAVA

	ListView list = (ListView)findViewById(R.id.list);
	PullToRefresh ptr = (PullToRefresh) findViewById(R.id.pull_to_refresh);
	
	ptr.setListView(list);
	ptr.setOnRefreshListener(new PullToRefresh.OnRefreshListener() {
	    @Override
	    public void onRefresh() {
	        runOnUiThread(new Runnable() {
	            @Override
	            public void run() {
	                // some stuff...
	  
	                ptr.refreshComplete();
	            }
	        });
	    }
	});
