<script>
    import Button from './shared/button.svelte'
    let fields= {question: '', answerA: '', answerB: ''}
    let errors = {question: '', answerA: '', answerB: ''}
    let valid = false

    const submitHandler =()=>{
        valid = true

    // validate question
        if (fields.question.trim().length < 5){
            valid=false
            errors.question = 'Question must be 5 characters or more'
        } else {errors.question=''
        }

    // validate answer A
    if (fields.answerA.trim().length < 1){
            valid=false
            errors.answerA = 'Answer A cannot be empty'
    } else {errors.answerA=''
    }   

    // validate answer B
    if (fields.answerB.trim().length < 1){
            valid=false
            errors.answerB = 'Answer B cannot be empty'
    } else {errors.answerB=''
    } 

        // create new poll
        if(valid){
            console.log('valid', fields)
        }
    }

</script>

<form on:submit|preventDefault={submitHandler}>
    <div class="form-field">
        <div class="error">{errors.question} </div>
        <label for="question">Poll Question:</label>
        <input type="text" id="question" bind:value={fields.question}>
    </div>
    <div class="form-field">
        <div class="error">{errors.answerA} </div>
        <label for="answer-a">Answer A</label>
        <input type="text" id="answer-a" bind:value={fields.answerA}>
    </div>
    <div class="form-field">
        <div class="error">{errors.answerB} </div>
        <label for="answer-b">Answer B</label>
        <input type="text" id="answer-b" bind:value={fields.answerB}>
    </div>
    <Button type='secondary' flat={true}>GO!</Button>
</form>

<style>
    form{
        width: 400px;
        margin: 0 auto;
        text-align: center;
    }
    .form-field{
        margin: 18px auto;
    }
    input{
        width: 100%;
        border-radius: 6px;
    }
    label{
        margin: 10px auto;
        text-align: left;
    }
    .error{
        font-weight: bold;
        font-size: 0.75rem;
        color: red;
    }
</style>