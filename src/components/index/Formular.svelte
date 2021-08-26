<style>
  form {
    display: flex;
    flex-direction: row;
    justify-content: center;
    align-content: center;
    margin: auto;
    z-index: 99999;
    position: relative;
    width: 85vw;
  }
  .inputsRight {
    display: flex;
    flex-direction: column;
  }
  input, textarea {
    width: 30vw;
    border-radius: var(--mainBorderRadius);
    border: none;
    box-shadow: var(--mainBoxShadow);
    padding: 10px;
    background-color: #ffffff;
    transition: 0.15s;
    transform-origin: left;
    border: 1px transparent solid;
    box-sizing: border-box;
    margin: 5px;
  }
  input[type="submit"] {
    font-family: var(--headingFont);
    font-size: 1.2em;
    background-color: var(--mainColor);
    color: #ffffff;
  }
  input[type="submit"]:hover {
    cursor: pointer;
    border: 1px var(--brandingColor) solid;
  }
  input:hover, textarea:hover {
    border: 1px var(--mainColor) solid;
  }
  input:focus, textarea:focus {
    border: 1px var(--mainColor) solid;
    outline: unset;
  }
  textarea {
    resize: none;
  }

  @media screen and (max-width: 770px) {
    form {
      flex-direction: column;
    }
    textarea {
      height: 120px;
    }
    textarea, input {
      width: 100%;
    }
  }
</style>


<form>  
  <textarea placeholder="Ich möchte Ihnen mitteilen..."></textarea>
  <div class="inputsRight">
    <input placeholder="Mein Name lautet..." type="text" />
    <input placeholder="Meine Email, sodass Sie mir antworten können..." type="email" />
    <input type="submit" value="Nachricht senden" />
  </div>
</form>
