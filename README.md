# AndroidImageSlider-1.5.0
Você está pronto para elevar o design dos seus aplicativos Android ao próximo nível? Apresentamos o AndroidImageSlider v1.5.0, uma poderosa biblioteca de código aberto que permite criar sliders de imagens deslumbrantes, modernos e altamente personalizáveis com facilidade.
Por que escolher o AndroidImageSlider?

Desempenho Superior: Otimizado para garantir que seus sliders sejam suaves e responsivos, mesmo com grandes conjuntos de imagens.
Fácil Integração: Com apenas algumas linhas de código, você pode adicionar sliders dinâmicos ao seu aplicativo, melhorando instantaneamente a interface do usuário.
Altamente Customizável: Adapte o slider ao estilo do seu aplicativo com várias opções de personalização, desde animações até layouts exclusivos.
Compatível com as Últimas Tecnologias: Totalmente compatível com as versões mais recentes do Android e otimizado para desempenho em dispositivos modernos.
💡 Por que Contribuir?

Como um projeto open-source sob a Licença Apache 2.0, o AndroidImageSlider não é apenas para uso — é para ser aprimorado. Aqui está sua chance de fazer parte de uma comunidade vibrante de desenvolvedores que estão moldando o futuro das interfaces visuais em dispositivos móveis.

Colabore e Aprenda: Trabalhe ao lado de outros desenvolvedores talentosos, compartilhe conhecimento e melhore suas habilidades.
Faça a Diferença: Suas contribuições podem ajudar milhares de desenvolvedores em todo o mundo a criar aplicativos incríveis.
Seja Reconhecido: Toda contribuição é valorizada, e você terá seu nome associado a um projeto utilizado por desenvolvedores globalmente.
🔧 Como Contribuir?

Faça o fork do repositório no GitHub.
Implemente novas funcionalidades, corrija bugs ou melhore a documentação.
Envie um Pull Request com suas mudanças.
E, claro, siga os termos da Licença Apache 2.0 — é simples e permite que você contribua com total segurança e clareza sobre seus direitos.
🌍 Junte-se a Nós!

Baixe o AndroidImageSlider v1.5.0 hoje e comece a criar experiências visuais que irão encantar seus usuários. Se você está animado para ir além e contribuir, estamos ansiosos para ver suas ideias ganharem vida. Juntos, podemos construir algo extraordinário!

📥 Download Agora | 💻 Contribua no GitHub


                                                        ->////////////////////////////////////////////////////////////////<-



# Android image slider
[ ![Download](https://api.bintray.com/packages/smarteistbintray/android/androidautoimageslider/images/download.svg) ](https://bintray.com/smarteistbintray/android/androidautoimageslider/_latestVersion)[![Android Arsenal](https://img.shields.io/badge/Android%20Arsenal-Android%20Slider-brightgreen.svg?style=flat)](https://android-arsenal.com/details/1/7693)  [![Apk](https://img.shields.io/badge/download-apk-yellowgreen.svg)](https://raw.githubusercontent.com/android-arsenal/apk31/master/7693/app.apk)

[![API](https://img.shields.io/badge/API-15%2B-brightgreen.svg?style=flat)](https://android-arsenal.com/api?level=15)
[![License](https://img.shields.io/badge/License-Apache%202.0-blue.svg)](https://opensource.org/licenses/Apache-2.0)


This is an amazing image slider for the Android .
 
You can easily load images with your custom layout, and there are many kinds of amazing animations you can choose.

```groovy
     implementation 'com.github.smarteist:autoimageslider:1.4.0'
```
If you are using appcompat libraries use this one, but please migrate to androidx as soon as you can.
```groovy
     implementation 'com.github.smarteist:autoimageslider:1.4.0-appcompat'
```

### New Feautures
* Ability to disable default indicator.

### New Changes
* Auto cycle bugs fixed.
* Swiping debounce implemented.


## Demo
![](https://github.com/smarteist/android-image-slider/blob/master/gif/0.gif)
![](https://github.com/smarteist/android-image-slider/blob/master/gif/8.gif)
![](https://github.com/smarteist/android-image-slider/blob/master/gif/4.gif)
![](https://github.com/smarteist/android-image-slider/blob/master/gif/7.gif)

## Integration guide

First put the slider view in your layout xml :

```xml
        <com.smarteist.autoimageslider.SliderView
                    android:id="@+id/imageSlider"
                    android:layout_width="match_parent"
                    android:layout_height="300dp"
                    app:sliderAnimationDuration="600"
                    app:sliderAutoCycleDirection="back_and_forth"
                    app:sliderAutoCycleEnabled="true"
                    app:sliderIndicatorAnimationDuration="600"
                    app:sliderIndicatorGravity="center_horizontal|bottom"
                    app:sliderIndicatorMargin="15dp"
                    app:sliderIndicatorOrientation="horizontal"
                    app:sliderIndicatorPadding="3dp"
                    app:sliderIndicatorRadius="2dp"
                    app:sliderIndicatorSelectedColor="#5A5A5A"
                    app:sliderIndicatorUnselectedColor="#FFF"
                    app:sliderScrollTimeInSec="1"
                    app:sliderStartAutoCycle="true" />
```

Or you can put it inside the cardView to look more beautiful :

```xml
       <androidx.cardview.widget.CardView
               app:cardCornerRadius="6dp"
               android:layout_margin="16dp"
               android:layout_width="match_parent"
               android:layout_height="wrap_content">

               <com.smarteist.autoimageslider.SliderView
                           android:id="@+id/imageSlider"
                           android:layout_width="match_parent"
                           android:layout_height="300dp"
                           app:sliderAnimationDuration="600"
                           app:sliderAutoCycleDirection="back_and_forth"
                           app:sliderAutoCycleEnabled="true"
                           app:sliderIndicatorAnimationDuration="600"
                           app:sliderIndicatorGravity="center_horizontal|bottom"
                           app:sliderIndicatorMargin="15dp"
                           app:sliderIndicatorOrientation="horizontal"
                           app:sliderIndicatorPadding="3dp"
                           app:sliderIndicatorRadius="2dp"
                           app:sliderIndicatorSelectedColor="#5A5A5A"
                           app:sliderIndicatorUnselectedColor="#FFF"
                           app:sliderScrollTimeInSec="1"
                           app:sliderStartAutoCycle="true" />

       </androidx.cardview.widget.CardView>
```

## Next step

The new version requires an slider adapter plus your custom layout for slider items, Although its very similar to RecyclerView & RecyclerAdapter, and it's familiar and easy to implement this adapter... here is an example for adapter implementation :

```java
public class SliderAdapterExample extends
        SliderViewAdapter<SliderAdapterExample.SliderAdapterVH> {

    private Context context;
    private List<SliderItem> mSliderItems = new ArrayList<>();

    public SliderAdapterExample(Context context) {
        this.context = context;
    }

    public void renewItems(List<SliderItem> sliderItems) {
        this.mSliderItems = sliderItems;
        notifyDataSetChanged();
    }

    public void deleteItem(int position) {
        this.mSliderItems.remove(position);
        notifyDataSetChanged();
    }

    public void addItem(SliderItem sliderItem) {
        this.mSliderItems.add(sliderItem);
        notifyDataSetChanged();
    }

    @Override
    public SliderAdapterVH onCreateViewHolder(ViewGroup parent) {
        View inflate = LayoutInflater.from(parent.getContext()).inflate(R.layout.image_slider_layout_item, null);
        return new SliderAdapterVH(inflate);
    }

    @Override
    public void onBindViewHolder(SliderAdapterVH viewHolder, final int position) {

        SliderItem sliderItem = mSliderItems.get(position);

        viewHolder.textViewDescription.setText(sliderItem.getDescription());
        viewHolder.textViewDescription.setTextSize(16);
        viewHolder.textViewDescription.setTextColor(Color.WHITE);
        Glide.with(viewHolder.itemView)
                .load(sliderItem.getImageUrl())
                .fitCenter()
                .into(viewHolder.imageViewBackground);

        viewHolder.itemView.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View v) {
                Toast.makeText(context, "This is item in position " + position, Toast.LENGTH_SHORT).show();
            }
        });
    }

    @Override
    public int getCount() {
        //slider view count could be dynamic size
        return mSliderItems.size();
    }

    class SliderAdapterVH extends SliderViewAdapter.ViewHolder {

        View itemView;
        ImageView imageViewBackground;
        ImageView imageGifContainer;
        TextView textViewDescription;

        public SliderAdapterVH(View itemView) {
            super(itemView);
            imageViewBackground = itemView.findViewById(R.id.iv_auto_image_slider);
            imageGifContainer = itemView.findViewById(R.id.iv_gif_container);
            textViewDescription = itemView.findViewById(R.id.tv_auto_image_slider);
            this.itemView = itemView;
        }
    }

}
```

## Custom Slider Image Layout

you can make your own layout for slider view

here is an example for adapter implementation :

```xml
<?xml version="1.0" encoding="utf-8"?>
<FrameLayout xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:orientation="vertical">

    <ImageView
        android:id="@+id/iv_auto_image_slider"
        android:layout_width="match_parent"
        android:layout_height="match_parent"
        android:scaleType="fitXY" />


    <ImageView
        android:id="@+id/iv_gif_container"
        android:layout_width="80dp"
        android:layout_height="80dp"
        android:layout_gravity="bottom|start"
        android:layout_margin="50dp" />


    <FrameLayout
        android:id="@+id/fl_shadow_container"
        android:background="@drawable/bg_overlay"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:layout_gravity="bottom">

        <TextView
            android:id="@+id/tv_auto_image_slider"
            android:layout_width="match_parent"
            android:layout_height="wrap_content"
            android:layout_marginTop="8dp"
            android:layout_marginBottom="25dp"
            android:padding="6dp"
            android:textColor="#FFF"
            android:textSize="18sp" />

    </FrameLayout>

</FrameLayout>
```

## Set the adapter to the Sliderview

After the instantiating of the sliderView (inside the activity or fragment with findViewById|BindView...), set the adapter to the slider.

```java
    SliderView sliderView = findViewById(R.id.imageSlider);
    sliderView.setSliderAdapter(new SliderAdapterExample(context));
```

You can call this method if you want to start flipping automatically and you can also set up the slider animation :

```java
    sliderView.setIndicatorAnimation(IndicatorAnimationType.WORM);
    sliderView.setSliderTransformAnimation(SliderAnimations.SIMPLETRANSFORMATION);
    sliderView.startAutoCycle();
```

## Elaborate more?

Here is a more realistic and more complete example :

```java

        @Override
        protected void onCreate(Bundle savedInstanceState) {
            super.onCreate(savedInstanceState);
            setContentView(R.layout.activity_main);

            SliderView sliderView = findViewById(R.id.imageSlider);

            SliderAdapterExample adapter = new SliderAdapterExample(this);

            sliderView.setSliderAdapter(adapter);

            sliderView.setIndicatorAnimation(IndicatorAnimationType.WORM); //set indicator animation by using IndicatorAnimationType. :WORM or THIN_WORM or COLOR or DROP or FILL or NONE or SCALE or SCALE_DOWN or SLIDE and SWAP!!
            sliderView.setSliderTransformAnimation(SliderAnimations.SIMPLETRANSFORMATION);
            sliderView.setAutoCycleDirection(SliderView.AUTO_CYCLE_DIRECTION_BACK_AND_FORTH);
            sliderView.setIndicatorSelectedColor(Color.WHITE);
            sliderView.setIndicatorUnselectedColor(Color.GRAY);
            sliderView.setScrollTimeInSec(4); //set scroll delay in seconds :
            sliderView.startAutoCycle();

        }
```

## Contribute

Suggestions and pull requests are always welcome.
Special Thanks [Roman Danylyk] (https://github.com/romandanylyk) for nice indicator!

## Licence

Copyright [2019] [Ali Hosseini]

   Licensed under the Apache License, Version 2.0;
   you may not use this file except in compliance with the License.
   You may obtain a copy of the License at

     http://www.apache.org/licenses/LICENSE-2.0

   Unless required by applicable law or agreed to in writing, software
   distributed under the License is distributed on an "AS IS" BASIS,
   WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
   See the License for the specific language governing permissions and
   limitations under the License.
 
