            SmartLocation.with(this).location()
                    .oneFix()
                    .start(new OnLocationUpdatedListener() {
                        @Override
                        public void onLocationUpdated(Location location) {

                            SmartLocation.with(MainDashboard.this).geocoding()
                                    .reverse(location, new OnReverseGeocodingListener() {
                                        @Override
                                        public void onAddressResolved(Location location, List<Address> list) {

                                            if (BuildConfig.DEBUG) {
                                                Toast.makeText(MainDashboard.this, "Total Location : "+list.size(), Toast.LENGTH_SHORT).show();
                                            }

                                            if (list.size() > 0) {
                                                Address result = list.get(0);
                                                StringBuilder builder = new StringBuilder();
                                                builder.append(text);
                                                List<String> addressElements = new ArrayList<>();
                                                for (int i = 0; i <= result.getMaxAddressLineIndex(); i++) {
                                                    addressElements.add(result.getAddressLine(i));
                                                }
                                                if (BuildConfig.DEBUG) {
                                                    Toast.makeText(MainDashboard.this, "Total AddressLine : "+result.getMaxAddressLineIndex(), Toast.LENGTH_SHORT).show();
                                                }
                                                builder.append(TextUtils.join(", ", addressElements));
                                                txtUserAddress.setText(builder.toString());
                                            }else{
                                                txtUserAddress.setText("No Address Found");
                                            }
                                        }
                                    });
                        }
                    });
