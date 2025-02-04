# PetCare Library

The **PetCare Library** is an Android library that provides an easy-to-use interface for integrating with the **PetCare API**. It allows developers to perform pet-related operations such as adding, updating, deleting, fetching all pets, searching pets by name, and filtering pets based on vaccination status.

## 📌 Features

- Fetch all pets from the database
- Add a new pet
- Search for a pet by name
- Update pet information
- Delete a pet by name
- Retrieve pets vaccinated within a specific time frame

---

## 🚀 Installation

To integrate the **PetCare Library** into your Android project, follow these steps:

### Step 1: Add the Dependency

The library is hosted on **JitPack**, so add it to your `build.gradle` file:

#### **Project-level `build.gradle`**
```gradle
allprojects {
    repositories {
        mavenCentral()
        maven { url 'https://jitpack.io' }
    }
}

App-level build.gradle
dependencies {
    implementation 'com.github.YourUsername:PetCareLib:1.0.0'
    implementation(libs.retrofit)
    implementation(libs.converter.gson)
    implementation(libs.gson)
}


📖 Usage Example
Fetch All Pets
PetAPI petAPI = PetRetrofit.getInstance().getPetCareApi();

petAPI.getAllPets().enqueue(new Callback<List<Pet>>() {
    @Override
    public void onResponse(Call<List<Pet>> call, Response<List<Pet>> response) {
        if (response.isSuccessful() && response.body() != null) {
            List<Pet> pets = response.body();
            Log.d("PetCare", "Fetched pets: " + pets.size());
        }
    }

    @Override
    public void onFailure(Call<List<Pet>> call, Throwable t) {
        Log.e("PetCare", "Error fetching pets", t);
    }
});


📂 Project Structure

📁 PetCareLib/
 ┣ 📂 src/main/java/com/example/petcarelib/
 ┃ ┣ 📜 Pet.java
 ┃ ┣ 📜 PetAPI.java
 ┃ ┣ 📜 PetRetrofit.java
 ┃ ┣ 📜 PetAdapter.java
 ┃ ┗ 📜 PetRepository.java
 ┣ 📂 res/
 ┃ ┣ 📂 layout/
 ┃ ┃ ┗ 📜 item_pet.xml
 ┃ ┗ 📂 values/
 ┃ ┃ ┗ 📜 strings.xml
 ┣ 📜 AndroidManifest.xml
 ┗ 📜 build.gradle


 📜 License
This project is licensed under the MIT License. See the LICENSE file for details.


📞 Support & Contributions
	•	If you find any issues, please open an issue in the repository.
	•	Contributions are welcome! Feel free to fork and create a pull request.