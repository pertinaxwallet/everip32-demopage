<script>
  import "./Styles.svelte";
  import { Icon, Input, Field, Details, Row, Col, Button } from "svelte-chota";
  import Loading from "./Loading.svelte";

  export let loaded;

  const allPermissions = [
    "ever_account",
    "ever_endpoint",
    "ever_sendTransaction",
    "ever_signMessage",
    "ever_getSignature",
    "ever_subscribe",
    "ever_unsubscribe",
    "ever_getNaclBoxPublicKey",
    "ever_encryptMessage",
    "ever_decryptMessage",
  ];

  const ever_module_method = (event) => {
    const ever_MODULE_METHOD_output = document.getElementById(
      "ever_MODULE_METHOD_output"
    );

    window.everscale
      .request({
        method: "ever_" + document.getElementById("ever_MODULE_METHOD_module").value  + "_" + document.getElementById("ever_MODULE_METHOD_method").value,
        params: JSON.parse(document.getElementById("ever_MODULE_METHOD_params").value),
      })
      .then((result) => {
        ever_MODULE_METHOD_output.innerText = JSON.stringify(result);
      })
      .catch((result) => {
        ever_MODULE_METHOD_output.innerText = JSON.stringify(result);
      });
  };

  const wallet_getSdkVersion = (event) => {
    const wallet_getSdkVersion_output = document.getElementById(
      "wallet_getSdkVersion_output"
    );

    window.everscale
      .request({
        method: "wallet_getSdkVersion",
        params: {},
      })
      .then((result) => {
        wallet_getSdkVersion_output.innerText = JSON.stringify(result);
      })
      .catch((result) => {
        wallet_getSdkVersion_output.innerText = JSON.stringify(result);
      });
  };

  const wallet_requestPermissions = (event) => {
    const wallet_requestPermissions_output = document.getElementById(
      "wallet_requestPermissions_output"
    );

    window.everscale
      .request({
        method: "wallet_requestPermissions",
        params: { permissions: allPermissions },
      })
      .then((result) => {
        wallet_requestPermissions_output.innerText = JSON.stringify(result);
      })
      .catch((result) => {
        wallet_requestPermissions_output.innerText = JSON.stringify(result);
      });
  };

  const wallet_getPermissions = async (event) => {
    const wallet_getPermissions_output = document.getElementById(
      "wallet_getPermissions_output"
    );

    window.everscale
      .request({
        method: "wallet_getPermissions",
        params: {},
      })
      .then((result) => {
        wallet_getPermissions_output.innerText = JSON.stringify(result);
      })
      .catch((result) => {
        wallet_getPermissions_output.innerText = JSON.stringify(result);
      });
  };

  const ever_account = (event) => {
    const ever_account_output = document.getElementById("ever_account_output");

    window.everscale
      .request({
        method: "ever_account",
        params: {},
      })
      .then((result) => {
        ever_account_output.innerText = JSON.stringify(result);
      })
      .catch((result) => {
        ever_account_output.innerText = JSON.stringify(result);
      });
  };

  const ever_endpoint = (event) => {
    const ever_endpoint_output = document.getElementById("ever_endpoint_output");

    window.everscale
      .request({
        method: "ever_endpoint",
        params: {},
      })
      .then((result) => {
        ever_endpoint_output.innerText = JSON.stringify(result);
      })
      .catch((result) => {
        ever_endpoint_output.innerText = JSON.stringify(result);
      });
  };

  const ever_sendTransaction = (event) => {
    const ever_sendTransaction_output = document.getElementById(
      "ever_sendTransaction_output"
    );

    window.everscale
      .request({
        method: "ever_sendTransaction",
        params: {
          destination: document.getElementById(
            "ever_sendTransaction_destination"
          ).value,
          amount: Number(
            document.getElementById("ever_sendTransaction_amount").value
          ).valueOf(),
          message: document.getElementById("ever_sendTransaction_message").value,
        },
      })
      .then((result) => {
        ever_sendTransaction_output.innerText = JSON.stringify(result);
      })
      .catch((result) => {
        ever_sendTransaction_output.innerText = JSON.stringify(result);
      });
  };

  const ever_signMessage = (event) => {
    const ever_signMessage_output = document.getElementById(
      "ever_signMessage_output"
    );

    window.everscale
      .request({
        method: "ever_signMessage",
        params: { data: document.getElementById("ever_signMessage_data").value },
      })
      .then((result) => {
        ever_signMessage_output.innerText = JSON.stringify(result);
      })
      .catch((result) => {
        ever_signMessage_output.innerText = JSON.stringify(result);
      });
  };

  const ever_getNaclBoxPublicKey = (event) => {
    const ever_getNaclBoxPublicKey_output = document.getElementById(
      "ever_getNaclBoxPublicKey_output"
    );

    window.everscale
      .request({
        method: "ever_getNaclBoxPublicKey",
        params: {},
      })
      .then((result) => {
        ever_getNaclBoxPublicKey_output.innerText = JSON.stringify(result);
      })
      .catch((result) => {
        ever_getNaclBoxPublicKey_output.innerText = JSON.stringify(result);
      });
  };

  const ever_getSignature = (event) => {
    const ever_getSignature_output = document.getElementById(
      "ever_getSignature_output"
    );

    window.everscale
      .request({
        method: "ever_getSignature",
        params: {
          data: document.getElementById("ever_getSignature_data").value,
        },
      })
      .then((result) => {
        ever_getSignature_output.innerText = JSON.stringify(result);
      })
      .catch((result) => {
        ever_getSignature_output.innerText = JSON.stringify(result);
      });
  };

  const ever_crypto_generate_random_bytes = (event) => {
    const ever_crypto_generate_random_bytes_output = document.getElementById(
      "ever_crypto_generate_random_bytes_output"
    );

    window.everscale
      .request({
        method: "ever_crypto_generate_random_bytes",
        params: {
          length: Number(
            document.getElementById("ever_crypto_generate_random_bytes_length")
              .value
          ).valueOf(),
        },
      })
      .then((result) => {
        ever_crypto_generate_random_bytes_output.innerText = JSON.stringify(
          result
        );
      })
      .catch((result) => {
        ever_crypto_generate_random_bytes_output.innerText = JSON.stringify(
          result
        );
      });
  };

  const ever_encryptMessage = (event) => {
    const ever_encryptMessage_output = document.getElementById(
      "ever_encryptMessage_output"
    );

    window.everscale
      .request({
        method: "ever_encryptMessage",
        params: {
          decrypted: document.getElementById("ever_encryptMessage_decrypted")
            .value,
          nonce: document.getElementById("ever_encryptMessage_nonce").value,
          their_public: document.getElementById(
            "ever_encryptMessage_their_public"
          ).value,
        },
      })
      .then((result) => {
        ever_encryptMessage_output.innerText = JSON.stringify(result);
      })
      .catch((result) => {
        ever_encryptMessage_output.innerText = JSON.stringify(result);
      });
  };

  const ever_decryptMessage = (event) => {
    const ever_decryptMessage_output = document.getElementById(
      "ever_decryptMessage_output"
    );

    window.everscale
      .request({
        method: "ever_decryptMessage",
        params: {
          encrypted: document.getElementById("ever_decryptMessage_encrypted")
            .value,
          nonce: document.getElementById("ever_decryptMessage_nonce").value,
          their_public: document.getElementById(
            "ever_decryptMessage_their_public"
          ).value,
        },
      })
      .then((result) => {
        ever_decryptMessage_output.innerText = JSON.stringify(result);
      })
      .catch((result) => {
        ever_decryptMessage_output.innerText = JSON.stringify(result);
      });
  };

  const ever_subscribe = (event) => {
    const ever_subscribe_output = document.getElementById(
      "ever_subscribe_output"
    );

    let filter;

    try {
      filter = JSON.parse(document.getElementById("ever_subscribe_filter").value);
    } catch(e) {
      ever_subscribe_output.innerText = "Filter must be valid JSON object";
      return;
    }

    window.everscale
      .request({
        method: "ever_subscribe",
        params: {
          collection: document.getElementById("ever_subscribe_collection").value,
          filter: filter,
          result: document.getElementById("ever_subscribe_result").value,
        },
      })
      .then((result) => {
        ever_subscribe_output.innerText = JSON.stringify(result);
      })
      .catch((result) => {
        ever_subscribe_output.innerText = JSON.stringify(result);
      });
  };

  const ever_unsubscribe = (event) => {
    const ever_unsubscribe_output = document.getElementById(
      "ever_unsubscribe_output"
    );

    window.everscale
      .request({
        method: "ever_unsubscribe",
        params: {
          handle: Number(
            document.getElementById("ever_unsubscribe_id").value
          ).valueOf(),
        },
      })
      .then((result) => {
        ever_unsubscribe_output.innerText = JSON.stringify(result);
      })
      .catch((result) => {
        ever_unsubscribe_output.innerText = JSON.stringify(result);
      });
  };

  const enable_listening_message = (event) => {
    const listening_message_output = document.getElementById(
      "listening_message_output"
    );

    window.everscale.on("message", function(event) {
      listening_message_output.innerText += JSON.stringify(event) + "\n";
    });
  };

  const disable_listening_message = (event) => {
    const listening_message_output = document.getElementById(
      "listening_message_output"
    );

    window.everscale.off("message");
    listening_message_output.innerText = '';
  };

  const enable_listening_endpointChanged = (event) => {
    const listening_endpointChanged_output = document.getElementById(
      "listening_endpointChanged_output"
    );

    window.everscale.on("endpointChanged", function(event) {
      listening_endpointChanged_output.innerText += JSON.stringify(event) + "\n";
    });
  };

  const disable_listening_endpointChanged = (event) => {
    const listening_endpointChanged_output = document.getElementById(
      "listening_endpointChanged_output"
    );

    window.everscale.off("endpointChanged");
    listening_endpointChanged_output.innerText = '';
  };

  const enable_listening_unlockStateChanged = (event) => {
    const listening_unlockStateChanged_output = document.getElementById(
      "listening_unlockStateChanged_output"
    );

    window.everscale.on("unlockStateChanged", function(event) {
      listening_unlockStateChanged_output.innerText += JSON.stringify(event) + "\n";
    });
  };

  const disable_listening_unlockStateChanged = (event) => {
    const listening_unlockStateChanged_output = document.getElementById(
      "listening_unlockStateChanged_output"
    );

    window.everscale.off("unlockStateChanged");
    listening_unlockStateChanged_output.innerText = '';
  };

  const enable_listening_accountChanged = (event) => {
    const listening_accountChanged_output = document.getElementById(
      "listening_accountChanged_output"
    );

    window.everscale.on("accountChanged", function(event) {
      listening_accountChanged_output.innerText += JSON.stringify(event) + "\n";
    });
  };

  const disable_listening_accountChanged = (event) => {
    const listening_accountChanged_output = document.getElementById(
      "listening_accountChanged_output"
    );

    window.everscale.off("accountChanged");
    listening_accountChanged_output.innerText = '';
  };

  const enable_listening_connect = (event) => {
    const listening_connect_output = document.getElementById(
      "listening_connect_output"
    );

    window.everscale.on("connect", function(event) {
      listening_connect_output.innerText += JSON.stringify(event) + "\n";
    });
  };

  const disable_listening_connect = (event) => {
    const listening_connect_output = document.getElementById(
      "listening_connect_output"
    );

    window.everscale.off("connect");
    listening_connect_output.innerText = '';
  };

  const enable_listening_disconnect = (event) => {
    const listening_disconnect_output = document.getElementById(
      "listening_disconnect_output"
    );

    window.everscale.on("disconnect", function(event) {
      listening_disconnect_output.innerText += JSON.stringify(event) + "\n";
    });
  };

  const disable_listening_disconnect = (event) => {
    const listening_disconnect_output = document.getElementById(
      "listening_disconnect_output"
    );

    window.everscale.off("disconnect");
    listening_disconnect_output.innerText = '';
  };
</script>

<style>
  .container {
    display: flex;
    padding-top: 2rem !important;
    flex-grow: 1;
    flex-direction: column;
  }
  .break-all {
    word-break: break-all;
    background-color: #efefef;
    padding: 1rem;
    font-weight: 600;
    border-radius: 4px;
  }
</style>

<div class="container">
  <h1 class="text-center">
    Demo page to test a browser wallet extension on EVERIP-32 (formerly TIP-32) compatibility
  </h1>
  {#if $loaded}
    <Row>
      <Col>
        <Details>
          <span slot="summary">ever_MODULE_METHOD</span>
          <Field label="Module">
            <Input id="ever_MODULE_METHOD_module" />
            <p>
            Specify a module name from <a href="https://github.com/tonlabs/TON-SDK/blob/master/docs/reference/types-and-methods">here</a>
            </p>
          </Field>
          <Field label="Method">
            <Input id="ever_MODULE_METHOD_method" />
            <p>
              Specify a method name for needed module. For example, for <b>client</b> module you can enter <b>version</b>. You can see method name for <b>client</b> module <a href="https://github.com/tonlabs/TON-SDK/blob/master/docs/reference/types-and-methods/mod_client.md"> here </a>
            </p>
          </Field>
          <Field label="Params">
            <Input textarea rows=4 id="ever_MODULE_METHOD_params" value="&lbrace; &rbrace;" />
            <p>
              Specify a params for needed method. They must be in JSON format.
            </p>
          </Field>
          <Field>
            <Button success on:click={ever_module_method}>Run SDK method</Button>
          </Field>
          <Field>
            <div class="break-all" id="ever_MODULE_METHOD_output" />
          </Field>
        </Details>

        <Details>
          <span slot="summary">wallet_getSdkVersion</span>
          <Field>
            <Button success on:click={wallet_getSdkVersion}>Get SDK version</Button>
          </Field>
          <Field>
            <div class="break-all" id="wallet_getSdkVersion_output" />
          </Field>
        </Details>

        <Details>
          <span slot="summary">wallet_requestPermissions</span>
          <Field>
            <Button success on:click={wallet_requestPermissions}>
              Request permissions
            </Button>
          </Field>
          <Field>
            <div class="break-all" id="wallet_requestPermissions_output" />
          </Field>
        </Details>

        <Details>
          <span slot="summary">wallet_getPermissions</span>
          <Field>
            <Button success on:click={wallet_getPermissions}>
              Get permissions
            </Button>
          </Field>
          <Field>
            <div class="break-all" id="wallet_getPermissions_output" />
          </Field>
        </Details>

        <Details>
          <span slot="summary">ever_account</span>
          <Field>
            <Button success on:click={ever_account}>Get current account</Button>
          </Field>
          <Field>
            <div class="break-all" id="ever_account_output" />
          </Field>
        </Details>

        <Details>
          <span slot="summary">ever_endpoint</span>
          <Field>
            <Button success on:click={ever_endpoint}>Get current endpoint</Button>
          </Field>
          <Field>
            <div class="break-all" id="ever_endpoint_output" />
          </Field>
        </Details>

        <Details>
          <span slot="summary">ever_sendTransaction</span>
          <Field label="Destination">
            <Input id="ever_sendTransaction_destination" />
            <p>
              You can select another account in your wallet and send between own
              accounts.
            </p>
          </Field>
          <Field label="Amount">
            <Input id="ever_sendTransaction_amount" type="number" />
            <p>You can use decimal number.</p>
          </Field>
          <Field label="Message">
            <Input id="ever_sendTransaction_message" />
            <p>
              This field is not required, but can be used for providing order ID or
              some additional information.
            </p>
          </Field>
          <Field>
            <Button success on:click={ever_sendTransaction}>
              Send transaction
            </Button>
          </Field>
          <Field>
            <div class="break-all" id="ever_sendTransaction_output" />
          </Field>
        </Details>

        <Details>
          <span slot="summary">ever_signMessage</span>
          <Field label="Data">
            <Input id="ever_signMessage_data" />
          </Field>
          <Field>
            <Button success on:click={ever_signMessage}>Sign message</Button>
          </Field>
          <Field>
            <div class="break-all" id="ever_signMessage_output" />
          </Field>
        </Details>

        <Details>
          <span slot="summary">ever_getNaclBoxPublicKey</span>
          <Field>
            <Button success on:click={ever_getNaclBoxPublicKey}>
              Get nacl box public key
            </Button>
          </Field>
          <Field>
            <div class="break-all" id="ever_getNaclBoxPublicKey_output" />
          </Field>
        </Details>

        <Details>
          <span slot="summary">ever_getSignature</span>
          <Field label="Data">
            <Input id="ever_getSignature_data" />
          </Field>
          <Field>
            <Button success on:click={ever_getSignature}>Get signature</Button>
          </Field>
          <Field>
            <div class="break-all" id="ever_getSignature_output" />
          </Field>
        </Details>

        <Details>
          <span slot="summary">ever_crypto_generate_random_bytes</span>
          <Field label="Length">
            <Input id="ever_crypto_generate_random_bytes_length" type="number" />
          </Field>
          <Field>
            <Button success on:click={ever_crypto_generate_random_bytes}>
              Crypto generate random bytes
            </Button>
          </Field>
          <Field>
            <div class="break-all" id="ever_crypto_generate_random_bytes_output" />
          </Field>
        </Details>

        <Details>
          <span slot="summary">ever_encryptMessage</span>
          <Field label="Decrypted">
            <Input id="ever_encryptMessage_decrypted" />
          </Field>
          <Field label="Nonce">
            <Input id="ever_encryptMessage_nonce" />
          </Field>
          <Field label="Their public">
            <Input id="ever_encryptMessage_their_public" />
          </Field>
          <Field>
            <Button success on:click={ever_encryptMessage}>Encrypt message</Button>
          </Field>
          <Field>
            <div class="break-all" id="ever_encryptMessage_output" />
          </Field>
        </Details>

        <Details>
          <span slot="summary">ever_decryptMessage</span>
          <Field label="Encrypted">
            <Input id="ever_decryptMessage_encrypted" />
          </Field>
          <Field label="Nonce">
            <Input id="ever_decryptMessage_nonce" />
          </Field>
          <Field label="Their public">
            <Input id="ever_decryptMessage_their_public" />
          </Field>
          <Field>
            <Button success on:click={ever_decryptMessage}>Decrypt message</Button>
          </Field>
          <Field>
            <div class="break-all" id="ever_decryptMessage_output" />
          </Field>
        </Details>

        <Details>
          <span slot="summary">ever_subscribe</span>
          <Field label="Collection">
            <Input id="ever_subscribe_collection" />
          </Field>
          <Field label="Filter">
            <Input id="ever_subscribe_filter" textarea />
          </Field>
          <Field label="Result">
            <Input id="ever_subscribe_result" />
          </Field>
          <Field>
            <Button success on:click={ever_subscribe}>Get subscription id</Button>
          </Field>
          <Field>
            <div class="break-all" id="ever_subscribe_output" />
          </Field>
        </Details>

        <Details>
          <span slot="summary">ever_unsubscribe</span>
          <Field label="Subscription id">
            <Input id="ever_unsubscribe_id" number />
          </Field>
          <Field>
            <Button success on:click={ever_unsubscribe}>Unsubscribe by id</Button>
          </Field>
          <Field>
            <div class="break-all" id="ever_unsubscribe_output" />
          </Field>
        </Details>
      </Col>
      <Col>
        <Details>
          <span slot="summary">Listen events "message"</span>
          <Field>
            <Button success on:click={enable_listening_message}>Enable listening</Button>
          </Field>
          <Field>
            <Button success on:click={disable_listening_message}>Disable listening</Button>
          </Field>
          <Field>
            <div class="break-all" id="listening_message_output" />
          </Field>
        </Details>

        <Details>
          <span slot="summary">Listen events "endpointChanged"</span>
          <Field>
            <Button success on:click={enable_listening_endpointChanged}>Enable listening</Button>
          </Field>
          <Field>
            <Button success on:click={disable_listening_endpointChanged}>Disable listening</Button>
          </Field>
          <Field>
            <div class="break-all" id="listening_endpointChanged_output" />
          </Field>
        </Details>

        <Details>
          <span slot="summary">Listen events "unlockStateChanged"</span>
          <Field>
            <Button success on:click={enable_listening_unlockStateChanged}>Enable listening</Button>
          </Field>
          <Field>
            <Button success on:click={disable_listening_unlockStateChanged}>Disable listening</Button>
          </Field>
          <Field>
            <div class="break-all" id="listening_unlockStateChanged_output" />
          </Field>
        </Details>

        <Details>
          <span slot="summary">Listen events "accountChanged"</span>
          <Field>
            <Button success on:click={enable_listening_accountChanged}>Enable listening</Button>
          </Field>
          <Field>
            <Button success on:click={disable_listening_accountChanged}>Disable listening</Button>
          </Field>
          <Field>
            <div class="break-all" id="listening_accountChanged_output" />
          </Field>
        </Details>

        <Details>
          <span slot="summary">Listen events "connect"</span>
          <Field>
            <Button success on:click={enable_listening_connect}>Enable listening</Button>
          </Field>
          <Field>
            <Button success on:click={disable_listening_connect}>Disable listening</Button>
          </Field>
          <Field>
            <div class="break-all" id="listening_connect_output" />
          </Field>
        </Details>

        <Details>
          <span slot="summary">Listen events "disconnect"</span>
          <Field>
            <Button success on:click={enable_listening_disconnect}>Enable listening</Button>
          </Field>
          <Field>
            <Button success on:click={disable_listening_disconnect}>Disable listening</Button>
          </Field>
          <Field>
            <div class="break-all" id="listening_disconnect_output" />
          </Field>
        </Details>
      </Col>
    </Row>
  {:else}
    <Loading />
  {/if}
</div>
