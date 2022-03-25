<script>
    import { createForm } from "svelte-forms-lib";
    import * as yup from "yup";

    const { form, errors, state, handleChange, handleSubmit } = createForm({
        initialValues: {
            name: "",
            email: ""
        },
        validationSchema: yup.object().shape({
            title: yup
                .string()
                .oneOf(["Mr.", "Mrs.", "Mx."])
                .required(),
            name: yup.string().required(),
            email: yup
                .string()
                .email()
                .required(),
            file: yup.mixed().required('File is required'),
        }),
        onSubmit: values => {
            console.log(values)
            alert(JSON.stringify(values));
        }
    });
</script>

<form on:submit={handleSubmit}>
    <label for="title">title</label>
    <select
            id="title"
            name="title"
            on:change={handleChange}
            bind:value={$form.title}>
        <option />
        <option>Mr.</option>
        <option>Mrs.</option>
        <option>Mx.</option>
    </select>
    {#if $errors.title}
        <small>{$errors.title}</small>
    {/if}

    <label for="name">name</label>
    <input
            id="name"
            name="name"
            on:change={handleChange}
            on:blur={handleChange}
            bind:value={$form.name}
    />
    {#if $errors.name}
        <small>{$errors.name}</small>
    {/if}

    <label for="email">email</label>
    <input
            id="email"
            name="email"
            on:change={handleChange}
            on:blur={handleChange}
            bind:value={$form.email}
    />
    {#if $errors.email}
        <small>{$errors.email}</small>
    {/if}

    <label for="file">Upload Picture</label>
    <input
            id="file"
            name="file"
            type="file"
            on:change={handleChange}
            on:blur={handleChange}
            bind:value={$form.file}
    />

    {#if $errors.file}
        <small>{$errors.file}</small>
    {/if}

    <button type="submit">submit</button>
</form>
