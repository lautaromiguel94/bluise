<template>
  <section class="blog">
    <div class="py-8 md:py-16 text-center">
      <h1 class="text-lg md:text-xl lg:text-4xl xl:text-6xl">Blog</h1>
      <h2 class="text-base md:text-lg lg:text-xl xl:text-2xl">
        Slow-carb messenger bag mlkshk fingerstache four dollar toast.
      </h2>
    </div>

    <div class="flex flex-wrap md:-mx-4 pb-20">
      <div v-for="(post, index) in posts" :key="index" class="w-full md:w-1/2 my-4 md:px-4">
        <div class="post">
          <nuxt-link :to="`/blog/${post.slug}`">
            <img
              :alt="post.title"
              class="w-full"
              :src="post.featuredImage || 'data:image/jpeg;base64,/9j/4AAQSkZJRgABAQAAAQABAAD/2wCEAAkGBwgHBgkIBwgKCgkLDRYPDQwMDRsUFRAWIB0iIiAdHx8kKDQsJCYxJx8fLT0tMTU3Ojo6Iys/RD84QzQ5OjcBCgoKDQwNGg8PGjclHyU3Nzc3Nzc3Nzc3Nzc3Nzc3Nzc3Nzc3Nzc3Nzc3Nzc3Nzc3Nzc3Nzc3Nzc3Nzc3Nzc3N//AABEIAL0AyAMBIgACEQEDEQH/xAAbAAABBQEBAAAAAAAAAAAAAAABAAIDBAUGB//EADwQAAEEAQIDBgMGAwcFAAAAAAEAAgMRBBIhBTFBBhMiUWGxMnFzFCQ0QoHRY5GhBxUjUlPB4RYzQ/Dx/8QAGAEBAQEBAQAAAAAAAAAAAAAAAAEDAgT/xAAdEQEAAwEAAwEBAAAAAAAAAAAAAQIRIQMSMUFh/9oADAMBAAIRAxEAPwDpKKRapaSpERaSjpKlpKkEWko6VJSVKCLQjpKkpGvRUxFpR0+ikISAUEelLSpP0SI2tUQ6SgQVPp80C0+SIgpKlMWppaioqSpPLUCETTNKbpUteaCgiITa81MQmubaCLShRUpCCCrmj7pP9N3skn534Sf6bvZBBr6UtKfSVKujAEdKdSSBulLSn0lSBtJUnUjpQMLfJNPh3dt/spQKBJ5BcL2y7SFpdhYchsEiRzfPyCk8Mbuf2iwcOUxuma5w6t3Cq/8AV+A6Jzmk6m9D1XmP+LkyhjS+R5O7WLbPZvKZjMfGHaq3aei49ncU1qTds5xLYbGG3sDf7rV4X2zxZS1uUDHfXmCuCn4dmxOJMTqHmFU77u3FrhTgd6/ZNJrj3OB8eRG2SF7XtI5tNj+aTm0vJOB9pMnhM4dC8mP8zHHYr1Lg3FsXjWIJ8V2/5mHm0+S7rLiYxOQmlqlc2k0hVya5oKjLPJTEIKKho9UFMWgqMtpAykKT/mlSaaq5zfuc5/hu9kk/N/BT/Td7JINVKk4BJA1Kk7SiAgalSdSJCobSW177D1TqVPPnjxcZ8sp8LRZUmcVjdr+PDh2CWQOAlfsHHovMIIMjiOSI4QXSPO5PkrnGs2bjPETo3GrTGzmuz7N8CZwyAPf45zzcsrWb+OmpOBcAg4fE2o7krd55rcbAGijyTmg9BXql4hzWevRkKs2IyUEEA36LE4h2S4dlnW+MscfzN2XSOBPp8kwtf+6RaUyHnGf2SmxL+zvErRyBFFU+BcUyuCcQEsbSyjUkZPxBemTRlwpwC47thw1giGXE3xNPjocx0VrZnakPQ8HLh4jhx5WMbY8XXl6KVzV5l2I7Q/3flfZZ3H7LMQLJ+F3Ren6mubqB2IBC9FZeWYxE4JqlcFGUQECLRSTQxzb5JpBClQItDFPO/BT/AE3eySOePuU/03eySI2KRpFKlVBJFFTQ2kk5ClQLoEnouG/tA4gWsZA01rJ1D08l282zHea8z7eWeKxsJoMZ+tklc2aUjqp2JwBNxB8zwCI2gix1K9EY6NnxEBcf2SLosCR8YGt76Fq7l4hyNp8qS76GrWEvTX433cUw49jM2+gtWWSRzN1NcP0XAPwYYptsmRw8iOS6fguS0sYxrtVenNR31su0tFrIzuKDFuwLCvZcmhhPkFy2dNHLIdY1WK3U4JXdqWufpMJrppN2jkZuLxDHkgJILxs1wq1FhQwQRl7Yg155ks3KmkbFkeFzBqHw7UR+yTyUx53NG/EzJIn7Oaf/AIvXeynEHZ/Bcd7jqeBpcfULzntdidzkwTdZBTj51X7rqP7N5XHhMwLvhmW1ZeW8O2JtN5poTmrRkBST9KaQmIakiUkVXzh9yn+m72SRzh9yn+m72SVGrSKSK5QEqRRVxQpKk5DddQqJ7dXhvYheaf2iDueIwTnbUyjfUg/8r01oo2RzXGdu8FnEO5YXNa+N2oX12WdpdU2ZxW7IRt/uQvc3fW5Vc/NmMz4cYNY6jUsl6b8h6rZ7NQGPgjGEblzvcqaXCjLfGCR5BYT9eysccNw+bOysl3250jYw3qwbuXV8FjPfMcLFDdWGcOZqtsewVzGiEJpoSZ1YjP0OJW6BwXNPYGk2CDq8RHP9F1GYHGM+qzGwslO4XPx3jkOI4E0vEA7HlkbA4g7yO1Dz6rTw/tMUx+J0H5NR8Q+ZW99ha3m0OsJwxWtfendWba4iuOf7aY3ecJimAsxv9x+4Uv8AZuT3GY3yeCtLj+Pr4RM3banf1UHZBkOK4xRQlhkbu7zWlJhheszuOuantTGqRm62eaTwmkI0iVTEZCCc4JqiIM78FP8ATd7JJZ34Kf6bvZJBsAI6UaRpFNoI0jSSpBUhSKSKY4LkeMAu4nM5w3DNl17/AOixOL4bnPbM2rcCwkjks7/G3gmPZU7PiuHCP8zXuCvuiAFBVeERdyx4uwSCCr0jqWEvTH1XIDRXkoX5GPigOnljYJK063VakedZ2Czc3AgzHMGTCJQ022+hSGi5m5cEOO6SV7WhosuJ2pZ0UsczosmB4dHJ1HVOzcOPKhdFK3XEdnNPUJuNBWlpADW7NaBQCSNJoAGyTmi0xj6FFPJtcuZZvG3d3w94IsPc0f13R4XG0zRPiFNDdVqTPYJO7adwHala4YyIGTQ4Eg6SP8uw2WlY6yvb1rLQBUjP9lEpGml6IeKUoQJQBTSVU0SmpJKSIM78FP8ATd7JJZv4Kf6bvZJBuIpJIpIUiiAgbSKKRCHTHNtRSsY9pbIPCeanpAtDm6XbjqmcWJmGY/CbjFr2vNHauQUEu61JI/8ACdGd6HhJWZJ8NlYXjHp8VvZnS50EMumR5aepAJA/VH7RjA6mvu/JTCNuu63PP1Uc8ONE0uA01uaC4rn69HEZycdpPjBvoqkmVjMsmUD9UWSYskmhrSPNSuxYWgERtvzIXUzBw2GePIj1wuJ+YpWGOUIY0C2iinagxpc8gABZpLK7RzTxQtfFKY9LSHOHmdh/VWeyMEkOIXOu5akId1v/ANCrTwu41PHGLbiRu1Od/qEdAulxYgxtgUOQryW9YeS9tTgWLTkQ2hSRWjIdktk20QqgEI0jzSr3QV80fcp/pu9kk7OH3Kf6bvZJVG3SNJ1JUim6UaRpFCDaSpOSRTSEgPNOQIREbyC3SB4gsPIe3vn6DqaHVY86Gy0c/JjgZqleGMAJcfZct2Z4kOLtznGiBKKaPyg8vZZXxt4uSuidhk0tIPyRmLHsLLABsWuc4vLNw3P8YPck2x/QqJ3GX6wNTSx5tY49Ps3W4bIjrHOtyU98rHN2duufm44XM0hwo9Vl5HFyzxONV6qddbDrjK1rdiP1QkBlx3X8JFb/ADWJ2fbLnXkSE91dAea280hmK4atFuAvyJOy6j6ztPFvAYSwDSAG2NlqClnYL/AAQNXoKBV9psWt6vJZKDtaaUgdqSXSAiEEgVEPanUg0JwVgV878FP9N3skjnD7lkekbvZFNG4kikqAgnBJDTUaTqSooGpjzpGrkN9ynlZnaDN+x8IypwaMcbiFyONy5p+0/F5ceJzm4OOLmeOvOmhWeyUbIcjPjb3elpZQj5DmtLs7w1/Duy/eSNLcrJaXG+l8vcrC7DQ5GKM5mWbm72j8hy91nP8AXor/AB0uZiQ5cZjnYHsPMFcTxfsfkMLjw6Xwh1hjtiu9O4tCtqIv5rl3rx4cG433piGNNrB6rZ4f2TnmBdnPpwPw816HNojiOw1H0VEg79LQQ40McEAjjaGtaOgpOMTJpYoXtDmufu09eZ/2T3jSC7rSXBvvXEJJf/Hjtqx1cR+w/qlY2UtPE82N9le3Tq0H4SenmrEZ2pXMqHvoS0fMKkyx8Qr0K2x55SgpJoTgq5JFBJBI0p4UQKkBQRZ34LJ+k72RTc4/cck/wneyKDdCNJwCNIG0UQE+kCWt3caHqugA1I7C+SjOU3kwWfmqjnvlm0ud4fJciwZG6tINuUcuBFlMLcgCRh5sPIprQI33pJvlSvRCm8qQhT4mxr4RGRQPIjpS4qIO4d2iycZzr79rZGX8qPsu5y26iS3cgdFw/a6N8XEMDMbyaDG4/wAiPcri8NfHLdjeCKUlqhBIHMY5p2cN1bLqFlZtTJWWN1UfSmllOn1VWQkCyiKfEZixpa3cnYDzW7wPCOJgNBAMjvE/1JWFwuF2ZxLUd2R7key6uOWJoDRK2/QhaUjji8/hEeJQSiMu0v2J3VpwDrIVPOFNBI3BpdskMjSzdu7UGvF0diopHODQGk77Jzqjj0+iCY7bFJNheCzS7mpC3y3RDVI0qMBEGkINzj9yyR/Cd7FJDN/A5HrE72KSK6WknOa1tlwHzRJ3IHNY2TPI+UgvOx2Co025DXuNCmjqVAJmyvp/w8lBE5xjc702ChgN2OoKIfkQmKUafhPJCu7kL+djZSl3eRuB5t3G6bG2zZ6FQXoGnu2axyCldNGwUXAKs6TwVZUAADgK2KokypQLe08/IrI49jszcB0bW+MeJvzWs6EEbdFVmheBYF/JczGuqzjkMLKdGdL7GnmPJbrcgPiDmmyR1VLjeKI5mZTG0150vHr5oQSXDQpYzycbx2NXCC517UoMqOWVhjx2F7j/ACHz8lJj3I5sbd3O2W0yIMYW6dvVdVrqWt6sXAxm8MxS3VrmedTj0/RVRB3sl6R86WpLGZpX6SA0bbJRwhq1iMhjM6pxvyoHDuXmvI7hXGzSzMqVgB8xyT2sANpEActkRBp1SjyCa8+M+XRTsbQ9VE9vxIGgEGwpmuJ5lR1fJOA0oiUckvP0TelJX4XE+SBuYbwMj6Tq/kkmTOvCyQf9J3skg6Fz9MDiCSszKBOUa6rTeB9kNbbKnK0DIcfIKgteI5WM8tiosmMxzlzeR3Qvxh3XUpeIHTIwjqOSAYpL3uHmFZYym0q3DTTnFXigBaCKpRuiJr0UwRU0V2agKRlaHN/ZPdzpNHwqoy+KQfasN0Q/y1fr0K5DHmlY5zRuW3YPou0lOl+3mQfULkO0EbcHi1w8pQXEeRv/AJWPlj9a+O2fW32bJyHSTV8PgF+fP2W3ku7uCmnxO23VLs/CyDhsOj8zQ8+pPNSZTy6WjybyWlYyHFp2TGNAbW+ycUGoqgVQtNAvmpa8KFIGad7UUgq/VWQFFL8NoiOJm1pPaCaU7AA1RH4kDSi4XE5IhOP/AGT6kIK0w+55I/hu9kk+cfdMn6TvZBB//9k='"
            />
            <div class="p-6 bg-white">
              <h2 class="text-2xl mb-2">{{ post.title }}</h2>

              <p class="text-base font-light">
                {{ post.excerpt }}
              </p>

              <h6 class="text-blue-600 mt-4 font-medium">Read more</h6>
            </div>
          </nuxt-link>
        </div>
      </div>
    </div>
    <Pagination v-if="totalPages > 1" :current-page="currentPage" :total-pages="totalPages" />
  </section>
</template>

<script lang="ts">
import { Component, Vue } from 'nuxt-property-decorator';
import { MetaInfo } from 'vue-meta';

const Pagination = () => import('@/components/commons/pagination.vue');

@Component({
  components: {
    Pagination,
  },

  head(): MetaInfo {
    return {
      title: 'Blog',
      meta: [
        {
          hid: 'description',
          name: 'description',
          content: 'Blog index',
        },
      ],
    };
  },
})
export default class BlogIndex extends Vue {
  currentPage!: number;

  totalPages!: number;

  posts: Post[] = [];

  async asyncData({ params, store }) {
    const page: number = params.page ? parseInt(params.page, 10) : 1;
    const { perPage }: { perPage: number } = store.state;
    const range = page * perPage;

    const posts = store.state.posts.filter((post, index) => {
      const indexPage = index + 1;
      return range - perPage < indexPage && indexPage <= range;
    });

    return {
      currentPage: page,
      totalPages: Math.ceil(store.state.posts.length / perPage),
      posts: posts || [],
    };
  }
}
</script>

<style lang="scss">
.blog {
  .post {
    @apply shadow-md;
    transition: all 0.2s cubic-bezier(0.64, 0, 0.35, 1);
    &:hover {
      @apply shadow-xl;
    }
  }
}
</style>
