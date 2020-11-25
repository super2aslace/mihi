private void Start() {
    FirebaseApp app = FirebaseApp.Create(
        new AppOptions()
        {
            DatabaseUrl = new Uri("https://test-project-a1c6e-matches.firebaseio.com/")
        }, 
        "matches"
    );
    DatabaseReference databaseReference = FirebaseDatabase.GetInstance(app)
        .GetReference("/path");
    databaseReference.ValueChanged += HandleChanged;
}

private void HandleChanged(object sender, ValueChangedEventArgs args) {
    // Do something
}        
