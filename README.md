# Receba nossas calorosas boas-vindas ao repositório do projeto `LockME`! 

Estamos felizes em tê-lo(a) aqui e esperamos que encontre todas as informações e recursos necessários para o desenvolvimento.

<details>
  <summary><strong>👨‍💻 O que deverá ser desenvolvido</strong></summary><br />

- Uma feature do android?
- Um app?
- Ambas opções?
  
</details>

<details>
  <summary><strong>⚠️ Antes de começar a desenvolver</strong></summary><br />

  1. Você precisa ter o AOSP instalado.

  - Use o comando: `sudo apt install aosp`.
  - recurso x versão 1.0
  
</details>

<details>
  <summary><strong>🏛️ Estrutura do Projeto</strong></summary><br />


  ```tree
.
├── src
│   ├──🔸palomakoba.palomakoba
│   ├──🔸 palomakoba2.palomakoba
│   ├── models
│   │   ├──🔸 palomakoba.palomakoba
│   └── services
│       ├──🔸palomakoba.palomakoba
├── tests
│   ├──🔸 test_palomakoba.palomakoba
├──🔸 README.md
├──🔸 dev-requirements.txt

 ```
</details>

<details>
  <summary><strong>💻Desenvolvimento</strong></summary><br />
    <details>
  <summary><strong>🌍 Sensor de Localização</strong></summary><br />
Para obter a coordenada atual (localização) no contexto do AOSP (Android Open Source Project), você precisa utilizar as APIs de localização do Android. Aqui está um exemplo básico de como obter a localização atual em um aplicativo Android:

1.Adicione a permissão necessária ao seu arquivo AndroidManifest.xml:
  ```tree
<uses-permission android:name="android.permission.ACCESS_FINE_LOCATION" />

 ```
2.No código da sua Activity ou Fragment, inicialize o gerenciador de localização e registre um ouvinte de localização para receber as atualizações de localização:

  ```tree
// Importe as classes necessárias
import android.Manifest;
import android.content.pm.PackageManager;
import android.location.Location;
import android.location.LocationListener;
import android.location.LocationManager;
import android.os.Bundle;
import androidx.core.app.ActivityCompat;
import androidx.appcompat.app.AppCompatActivity;

public class MainActivity extends AppCompatActivity implements LocationListener {
    private LocationManager locationManager;

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);

        // Inicialize o LocationManager
        locationManager = (LocationManager) getSystemService(LOCATION_SERVICE);

        // Verifique se a permissão de localização foi concedida
        if (ActivityCompat.checkSelfPermission(this, Manifest.permission.ACCESS_FINE_LOCATION) != PackageManager.PERMISSION_GRANTED) {
            // Se a permissão não foi concedida, solicite-a
            ActivityCompat.requestPermissions(this, new String[]{Manifest.permission.ACCESS_FINE_LOCATION}, 1);
        } else {
            // Se a permissão foi concedida, registre o ouvinte de localização
            locationManager.requestLocationUpdates(LocationManager.GPS_PROVIDER, 0, 0, this);
        }
    }

    // Implemente os métodos do LocationListener
    @Override
    public void onLocationChanged(Location location) {
        // Aqui você recebe as atualizações de localização
        double latitude = location.getLatitude();
        double longitude = location.getLongitude();

        // Faça o que desejar com as coordenadas
    }

    @Override
    public void onStatusChanged(String provider, int status, Bundle extras) {}

    @Override
    public void onProviderEnabled(String provider) {}

    @Override
    public void onProviderDisabled(String provider) {}
}

 ```
 Lembre-se de solicitar a permissão ACCESS_FINE_LOCATION no tempo de execução, se necessário. Você também pode usar o provedor NETWORK_PROVIDER para obter a localização usando a rede celular ou provedor de Wi-Fi em vez do GPS (GPS_PROVIDER) se a precisão não for crucial para o seu caso de uso.

Tenha em mente que esse é um exemplo básico e existem considerações adicionais para lidar com permissões, tratamento de erros e gerenciamento correto do ciclo de vida das atividades ou fragmentos ao usar a localização no Android.
  
</details>

  
</details>

<details>
  <summary><strong>🗣 Gostaríamos de receber feedbacks sobre o projeto!</strong></summary><br />

Por favor, sinta-se à vontade para compartilhar suas opiniões e sugestões sobre o projeto por meio de um email. Valorizamos muito o seu feedback, pois ele nos ajudará a melhorar e aperfeiçoar o trabalho realizado até o momento. Aguardamos ansiosamente por suas contribuições e agradecemos pelo tempo dedicado em nos fornecer seus comentários construtivos.

[✉️ almeidaa405@gmail.com](mailto:almeidaa405@gmail.com)

</details>

