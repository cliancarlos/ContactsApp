<template layout="AppShell,Guest">
  <div>
    <Head title="Email Verification" />

    <AuthLogo />

    <div class="tw-mb-4 tw-opacity-60">
      Thanks for signing up! Before getting started, could you verify your email address by clicking on the link we just emailed to you? If you didn't receive the email, we will gladly send you another.
    </div>

    <form @submit.prevent="form.post(route('verification.send'))">
      <div class="tw-mt-4 tw-flex tw-items-center tw-justify-between">
        <q-btn
          :disabled="form.processing"
          type="submit"
          color="primary"
        >
          Resend Verification Email
        </q-btn>

        <Link
          :href="route('logout')"
          method="post"
          as="button"
        >
          Log Out
        </Link>
      </div>
    </form>
  </div>
</template>

<script setup>
const form = useForm()
</script>
