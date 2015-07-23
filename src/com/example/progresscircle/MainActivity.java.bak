package com.example.progresscircle;


import com.example.progresscircle.view.CircleProgressBar;

import android.animation.ObjectAnimator;
import android.app.Activity;
import android.os.Bundle;
import android.os.Handler;
import android.view.animation.AccelerateDecelerateInterpolator;
import android.widget.TextView;


public class MainActivity extends Activity {

	// ProgressBar环形进度条
	private CircleProgressBar mAbProgressBar;
	// 最大100
	private int max = 100;
	private int progress = 0;
	private TextView numberText, maxText;

	@Override
	protected void onCreate(Bundle savedInstanceState) {
		super.onCreate(savedInstanceState);
		setContentView(R.layout.activity_main);

		// ProgressBar进度控制
		mAbProgressBar = (CircleProgressBar) findViewById(R.id.circleProgressBar);
		numberText = (TextView) findViewById(R.id.numberText);
		maxText = (TextView) findViewById(R.id.maxText);
		numberText.setText("80");
		maxText.setText("总共  " + String.valueOf(max));
		mAbProgressBar.setMax(max);
		progress = 80;
		new Thread(new Runnable() {
			
			@Override
			public void run() {
				// TODO Auto-generated method stub
				try {
					Thread.sleep(800);
					handle.sendEmptyMessage(1);
				} catch (InterruptedException e) {
					// TODO Auto-generated catch block
					e.printStackTrace();
				}
			}
		}).start();
		
		
	}
	public void startAnimator(int progress){
		int lastProgressValue = 360/100*progress;
		ObjectAnimator objectAnimator = ObjectAnimator.ofInt(mAbProgressBar, "progress", 0,lastProgressValue);
		objectAnimator.setInterpolator(new AccelerateDecelerateInterpolator());
		objectAnimator.setDuration(800);
		objectAnimator.start();
	}
	Handler handle = new Handler(){
		public void handleMessage(android.os.Message msg) {
			startAnimator(80);
		};
	};
}
