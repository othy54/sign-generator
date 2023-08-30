<template>
  <div class="page grid grid-cols-12">
    <aside class="bg-[#1B3930] col-span-2 h-screen px-8 py-10 flex flex-col gap-10 overflow-auto">
      <label>
        Photo de profil (ou logo)
        <input v-model="profil" type="text" name="firstname">
      </label>
      <label>
        Prénom
        <input v-model="firstname" type="text" name="firstname">
      </label>
      <label>
        Nom
        <input v-model="lastname" type="text" name="lastname">
      </label>
      <label>
        Poste
        <input v-model="job" type="text" name="job">
      </label>
      <label>
        Téléphone (personnel)
        <input v-model="phone" type="tel" name="phone">
      </label>
      <label>
        Société
        <input v-model="society" type="text" name="society">
      </label>
      <label>
        Slogan
        <input v-model="slogan" type="text" name="slogan">
      </label>
      <label>
        Téléphone (Société)
        <input v-model="phoneSociety" type="tel" name="phone-society">
      </label>
      <label>
        Couleur
        <input v-model="color" type="color" name="color">
      </label>
      <label>
        Lien site web (sans http et sans www)
        <input v-model="web" type="text" name="web">
      </label>
      <label>
        Logo footer
        <input v-model="logoFooter" type="text" name="logo-footer">
      </label>
      <label>
        Taille du logo footer
        <input v-model="widthLogoFooter" type="number" name="width-logo-footer">
      </label>

    </aside>
    <main  class="col-span-10">
      <div class="row padding-limit mt-20">
        <div class="container mx-auto h-full">
          <div
            id="content-signature"
            class="h-1/2 w-full flex justify-center items-center"
          >
            <div
              ref="copy"
              style="padding: 20px"
              class="border border-gray-200"
            >
              <table class="w-[800px]" style="border: 0">
                <tbody style="border: 0">
                  <tr style="border: 0">
                    <td>
                      <div style="display: flex">
                        <a
                          aria-hidden="true"
                          rel="noopener nofollow"
                          :href="'https://' + web"
                          target="_blank"
                          ><img
                            width="100"
                            :src="profil || '/images/avatar.png'"
                            alt="photo"
                        /></a>
                        <div :style="`margin-left: 25px; margin-top:20px;`">
                          <p style="margin: 0">
                            <span
                              :style="`text-transform: capitalize;
                              font-weight: 600;
                              margin-bottom: 3px;
                              color: #333;
                              font-size: 16px;`"
                            >
                              {{ firstname || 'John' }}
                            </span>
                            <span
                              :style="`text-transform: uppercase;
                              font-weight: 600;
                              margin-bottom: 3px;
                              color: #333;
                              font-size: 16px;`"
                            >
                              {{ ' ' + (lastname || 'Doe') }}
                            </span>
                          </p>

                          <p style="margin: 0">
                            {{ job || 'Directeur' }}
                          </p>
                          <p style="margin: 2px 0 5px 0">
                            <a :href="'tel:'+ phone">
                              {{ phone || '06 24 02 90 33' }}
                            </a>
                          </p>
                        </div>
                      </div>
                    </td>
                  </tr>
                  <tr style="border: 0">
                    <td style="padding-top: 15px">
                      <p style="margin-bottom: 0; margin-top: 0">
                        <b
                          ><a
                            aria-hidden="true"
                            :style="{ color: color }"
                            :href="'https://' + web"
                            target="_blank"
                            rel="noopener"
                            >{{ society || 'MA SOCIETE' }} -
                            {{ slogan || 'Mon slogan' }}</a
                          ></b
                        >
                      </p>
                      <p
                        :style="`
                          margin-top: 0;
                          margin-bottom:0;
                          display: flex;
                          border-bottom: 1.5px solid #33333320;
                          padding-bottom: 7px;`"
                      >
                        <span style="margin: 0">
                          <span>
                            <a
                              style="color: unset; text-decoration: unset"
                              href="tel:+33-3-57-75-96-63"
                              > {{ phoneSociety || '03 80 60 50 40' }}
                            </a>
                          </span>
                          <a
                              style="color: unset; text-decoration: unset"
                              :href="'https://' + web"
                              rel="noopener"
                              > | {{ 'www.' + (web || 'masociete.fr') }} </a
                            >
                          </span
                        >

                        <!-- <span style="padding-top: 4px; margin-left: 180px">
                          <a
                            style="display: inline-flex; align-items: center"
                            :href="[
                              selected === 'aleo'
                                ? 'https://www.facebook.com/aleo.agency/'
                                : 'https://www.facebook.com/nancomcy',
                            ]"
                            target="_blank"
                            ><img
                              :src="`https://static.nancomcy.fr/static/signatures/logo-facebook${aleoActive}.png`"
                              alt="fb logo"
                              width="18"
                              style="margin-right: 5px"
                          /></a>
                          <a
                            style="display: inline-flex; align-items: center"
                            :href="[
                              selected === 'aleo'
                                ? 'https://www.instagram.com/aleo.agency/'
                                : 'https://www.instagram.com/nancomcy/',
                            ]"
                            target="_blank"
                            ><img
                              :src="`https://static.nancomcy.fr/static/signatures/logo-instagram${aleoActive}.png`"
                              alt="insta logo"
                              width="18"
                              style="margin-right: 5px"
                          /></a>
                          <a
                            style="display: inline-flex; align-items: center"
                            :href="[
                              selected === 'aleo'
                                ? 'https://www.youtube.com/watch?v=QfvV5xR-H8Q'
                                : 'https://www.youtube.com/watch?v=dbe2B2IDjp0',
                            ]"
                            target="_blank"
                            ><img
                              :src="`https://static.nancomcy.fr/static/signatures/logo-youtube${aleoActive}.png`"
                              alt="youtube logo"
                              width="18"
                          /></a>
                        </span> -->
                      </p>
                    </td>
                  </tr>
                  <tr style="border: 0">
                    <td style="padding-top: 10px">
                      <img
                        :src="logoFooter"
                        :width="widthLogoFooter"
                      />
                    </td>
                  </tr>
                </tbody>
              </table>
            </div>
          </div>
        </div>
      </div>
      <div class="row">
        <div class="container mx-auto">
          <div
            class="bg-[#1B3930] text-center block w-max mx-auto text-white py-2 px-4 font-semibold text-xl rounded-md mt-10 cursor-pointer"
            @click="copyToClip"
          >
            Copier signature
          </div>
        </div>
      </div>
      <transition name="fade" class="row">
        <div v-if="copyDone" class="container mx-auto">
          <div
            class="text-center block w-max mx-auto text-greencustom py-2 px-4 font-semibold text-xl mt-10 cursor-pointer"
          >
            Signature copiée !
          </div>
        </div>
      </transition>
    </main>
  </div>
</template>
<script setup>
import "@fontsource/montserrat/400.css"
import "@fontsource/montserrat/600.css"
import "@fontsource/montserrat/700.css"

const profil = ref(null);
const firstname = ref('');
const lastname = ref('');
const job = ref('');
const phone = ref(null);
const society = ref('');
const slogan = ref('');
const phoneSociety = ref(null);
const web = ref('');
const color = ref(null);
const logoFooter = ref('');
const widthLogoFooter = ref(300);


const copy = ref(null);
const copyDone = ref(false);

const copyToClip = () => {
    const str = copy.value.innerHTML;
    console.log(str)
    function listener(e) {
      e.clipboardData.setData("text/html", str);
      e.preventDefault();
    }
    document.addEventListener("copy", listener);
    const success = document.execCommand("copy");
    if (success) {
      copyDone.value = true;
      setTimeout(() => {
        copyDone.value = false;
      }, 4000);
    }

    document.removeEventListener("copy", listener);
}

</script>
<style lang="postcss" scoped>

label {
  color: white;
  font-weight: 600;
  letter-spacing: 0.5px;
  font-family: 'Montserrat', sans-serif;
  display: flex;
  flex-direction: column;
}

input {
  color: white;
  background-color: transparent;
  border-bottom: 2px solid white;
  padding: 5px;
  font-weight: 500;
}

input[type="color"] {
  padding: 0;
  width: 100%
}

.fade-enter-active,
.fade-leave-active {
  transition: opacity 0.5s;
}
.fade-enter,
.fade-leave-to {
  opacity: 0;
}
</style>
