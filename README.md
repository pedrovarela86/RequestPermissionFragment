# RequestPermissionFragment
This is an abstract class, I use to easily request permissions in Android +6.0. To use it extend the abstract fragment in the fragments that needs to request permissions. 


public class MyFragment extends RequestPermissionFragment {
	@Override
	public void onPermissionsGranted(int requestCode) {
		
	}
	
	@Override
	public void onShouldShowRequestPermissionsRationale() {
		
	}
	
	@Override
	public void onPermissionsDenied(int requestCode) {
		
	}
}

Then, check the permission wherever you need it like this. 

private void setGoogleMapUISettings() {
		
		#if (ActivityCompat.checkSelfPermission(getContext(), Manifest.permission.ACCESS_FINE_LOCATION) != PackageManager.PERMISSION_GRANTED) {
			return;
		}
		
		mMap.setPadding(10, 20, 10, 10);
		
		mMap.setBuildingsEnabled(true);
		mMap.setTrafficEnabled(false);
		mMap.setMyLocationEnabled(true);
		mMap.setIndoorEnabled(false);
		
		mMap.getUiSettings().setCompassEnabled(false);
		mMap.getUiSettings().setMyLocationButtonEnabled(false);
		mMap.getUiSettings().setIndoorLevelPickerEnabled(false);
		mMap.getUiSettings().setMapToolbarEnabled(false);
		
	}
