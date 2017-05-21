# Pull To Refresh Library [ ![Download](https://api.bintray.com/packages/omaflak/maven/pull-to-refresh/images/download.svg) ](https://bintray.com/omaflak/maven/pull-to-refresh/_latestVersion)
Pull To Refresh with progress bar

# Gradle

Add to your gradle dependencies:

	compile 'me.aflak.libraries:pulltorefresh:1.0'
	
# Xml Layout

    <me.aflak.pulltorefresh.PullToRefresh
      android:id="@+id/pull_to_refresh"
      android:layout_width="match_parent"
      android:layout_height="match_parent">
	  
      <ListView
          android:id="@+id/list"
          android:layout_width="match_parent"
          android:layout_height="match_parent"/>
		  
    </me.aflak.pulltorefresh.PullToRefresh>
    
# Java file

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
