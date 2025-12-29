<script setup lang="ts">
import * as z from 'zod'
import type { FormSubmitEvent, AuthFormField } from '@nuxt/ui'

const toast = useToast()

const fields: AuthFormField[] = [
    {
        name: 'name',
        label: 'Name',
        type: 'text',
        placeholder: 'Enter your name',
        required: true
    },
    {
        name: 'email',
        type: 'email',
        label: 'Email',
        placeholder: 'Enter your email',
        required: true
    }, {
        name: 'password',
        label: 'Password',
        type: 'password',
        placeholder: 'Enter your password',
        required: true
    }, {
        name: 'remember',
        label: 'Remember me',
        type: 'checkbox'
    }]

const providers = [{
    label: 'Google',
    icon: 'i-simple-icons-google',
    onClick: () => {
        toast.add({ title: 'Google', description: 'Login with Google' })
    }
}, {
    label: 'GitHub',
    icon: 'i-simple-icons-github',
    onClick: () => {
        toast.add({ title: 'GitHub', description: 'Login with GitHub' })
    }
}]

const schema = z.object({
    name: z.string('Name is required').min(3, 'Must be at least 3 characters'),
    email: z.email('Invalid email'),
    password: z.string('Password is required').min(8, 'Must be at least 8 characters')
})

type Schema = z.output<typeof schema>

function onSubmit(payload: FormSubmitEvent<Schema>) {
    console.log('Submitted', payload)
}
</script>

<template>
    <div class="flex flex-col items-center justify-center gap-4 p-4">
        <UPageCard class="w-full max-w-md">
            <UAuthForm :schema="schema" title="Register" description="Create a new account." icon="i-lucide-user"
                :fields="fields" :providers="providers" @submit="onSubmit" />
        </UPageCard>
        <UButton to="/login" variant="link" color="primary" class="text-sm" label="Already have an account? Login" />
    </div>
</template>
