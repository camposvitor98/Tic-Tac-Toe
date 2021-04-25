<template>
  <div class="tableConteiner">
    <h2 v-if="setWinner">{{ setWinner }}!!</h2>
    <div class="table">
      <div class="row-a">
        <span
          class="a1"
          :class="currentClass.a1"
          @click="setCurrentClass(currentClass.a1)"
        >
          <p v-if="currentPlayer.a1 == 'a1'">A1</p>
          <img
            v-else-if="currentPlayer.a1 == 'Player 1'"
            src="https://img.icons8.com/windows/452/circled--v1.png"
            alt="Player 1"
          />
          <img
            v-else
            src="https://img.icons8.com/ios/452/x.png"
            alt="Player 2"
          />
        </span>
        <span
          class="b1"
          :class="currentClass.b1"
          @click="setCurrentClass(currentClass.b1)"
        >
          <p v-if="currentPlayer.b1 == 'b1'">B1</p>
          <img
            v-else-if="currentPlayer.b1 == 'Player 1'"
            src="https://img.icons8.com/windows/452/circled--v1.png"
            alt="Player 1"
          />
          <img
            v-else
            src="https://img.icons8.com/ios/452/x.png"
            alt="Player 2"
          />
        </span>
        <span
          class="c1"
          :class="currentClass.c1"
          @click="setCurrentClass(currentClass.c1)"
        >
          <p v-if="currentPlayer.c1 == 'c1'">C1</p>
          <img
            v-else-if="currentPlayer.c1 == 'Player 1'"
            src="https://img.icons8.com/windows/452/circled--v1.png"
            alt="Player 1"
          />
          <img
            v-else
            src="https://img.icons8.com/ios/452/x.png"
            alt="Player 2"
          />
        </span>
      </div>
      <div class="row-b">
        <span
          class="a2"
          :class="currentClass.a2"
          @click="setCurrentClass(currentClass.a2)"
        >
          <p v-if="currentPlayer.a2 == 'a2'">A2</p>
          <img
            v-else-if="currentPlayer.a2 == 'Player 1'"
            src="https://img.icons8.com/windows/452/circled--v1.png"
            alt="Player 1"
          />
          <img
            v-else
            src="https://img.icons8.com/ios/452/x.png"
            alt="Player 2"
          />
        </span>
        <span
          class="b2"
          :class="currentClass.b2"
          @click="setCurrentClass(currentClass.b2)"
        >
          <p v-if="currentPlayer.b2 == 'b2'">B2</p>
          <img
            v-else-if="currentPlayer.b2 == 'Player 1'"
            src="https://img.icons8.com/windows/452/circled--v1.png"
            alt="Player 1"
          />
          <img
            v-else
            src="https://img.icons8.com/ios/452/x.png"
            alt="Player 2"
          />
        </span>
        <span
          class="c2"
          :class="currentClass.c2"
          @click="setCurrentClass(currentClass.c2)"
        >
          <p v-if="currentPlayer.c2 == 'c2'">C2</p>
          <img
            v-else-if="currentPlayer.c2 == 'Player 1'"
            src="https://img.icons8.com/windows/452/circled--v1.png"
            alt="Player 1"
          />
          <img
            v-else
            src="https://img.icons8.com/ios/452/x.png"
            alt="Player 2"
          />
        </span>
      </div>
      <div class="row-c">
        <span
          class="a3"
          :class="currentClass.a3"
          @click="setCurrentClass(currentClass.a3)"
        >
          <p v-if="currentPlayer.a3 == 'a3'">A3</p>
          <img
            v-else-if="currentPlayer.a3 == 'Player 1'"
            src="https://img.icons8.com/windows/452/circled--v1.png"
            alt="Player 1"
          />
          <img
            v-else
            src="https://img.icons8.com/ios/452/x.png"
            alt="Player 2"
          />
        </span>
        <span
          class="b3"
          :class="currentClass.b3"
          @click="setCurrentClass(currentClass.b3)"
        >
          <p v-if="currentPlayer.b3 == 'b3'">B3</p>
          <img
            v-else-if="currentPlayer.b3 == 'Player 1'"
            src="https://img.icons8.com/windows/452/circled--v1.png"
            alt="Player 1"
          />
          <img
            v-else
            src="https://img.icons8.com/ios/452/x.png"
            alt="Player 2"
          />
        </span>
        <span
          class="c3"
          :class="currentClass.c3"
          @click="setCurrentClass(currentClass.c3)"
        >
          <p v-if="currentPlayer.c3 == 'c3'">C3</p>
          <img
            v-else-if="currentPlayer.c3 == 'Player 1'"
            src="https://img.icons8.com/windows/452/circled--v1.png"
            alt="Player 1"
          />
          <img
            v-else
            src="https://img.icons8.com/ios/452/x.png"
            alt="Player 2"
          />
        </span>
      </div>
    </div>
    <button
      v-show="countRounds != 0"
      v-if="!setWinner"
      class="reset-button"
      type="button"
      @click="reset"
    >
      Reiniciar partida!
    </button>
    <button v-else class="new-game-button" type="button" @click="reset">
      Iniciar novo jogo?
    </button>
  </div>
</template>

<script lang="ts">
interface ITable {
  a1: string;
  b1: string;
  c1: string;
  a2: string;
  b2: string;
  c2: string;
  a3: string;
  b3: string;
  c3: string;
}
interface IData {
  currentPlayer: ITable;
  lastClass: string;
  currentClass: ITable;
  player: string;
  setWinner: string;
  countRounds: number;
}
export default {
  data(): IData {
    return {
      countRounds: 0,
      player: "Player 1",
      lastClass: "red",
      currentClass: {
        a1: "a1",
        b1: "b1",
        c1: "c1",
        a2: "a2",
        b2: "b2",
        c2: "c2",
        a3: "a3",
        b3: "b3",
        c3: "c3"
      },
      currentPlayer: {
        a1: "a1",
        b1: "b1",
        c1: "c1",
        a2: "a2",
        b2: "b2",
        c2: "c2",
        a3: "a3",
        b3: "b3",
        c3: "c3"
      },
      setWinner: ""
    };
  },
  methods: {
    setCurrentClass(id: string) {
      // const setPlayer = this.player;
      if (id === "a1") {
        this.currentClass.a1 = this.lastClass;
        this.currentPlayer.a1 = this.player;
        this.countRounds += 1;

        this.winner();
        this.setNextPlayer();
        this.setNextClass();
        if (this.countRounds == 9 && !this.setWinner) {
          this.setWinner = "Empate";
        }
      } else if (id === "b1") {
        this.currentClass.b1 = this.lastClass;
        this.currentPlayer.b1 = this.player;
        this.countRounds += 1;

        this.winner();
        this.setNextPlayer();
        this.setNextClass();
        if (this.countRounds == 9 && !this.setWinner) {
          this.setWinner = "Empate";
        }
      } else if (id === "c1") {
        this.currentClass.c1 = this.lastClass;
        this.currentPlayer.c1 = this.player;
        this.countRounds += 1;

        this.winner();
        this.setNextPlayer();
        this.setNextClass();
        if (this.countRounds == 9 && !this.setWinner) {
          this.setWinner = "Empate";
        }
      } else if (id === "a2") {
        this.currentClass.a2 = this.lastClass;
        this.currentPlayer.a2 = this.player;
        this.countRounds += 1;

        this.winner();
        this.setNextPlayer();
        this.setNextClass();
        if (this.countRounds == 9 && !this.setWinner) {
          this.setWinner = "Empate";
        }
      } else if (id === "b2") {
        this.currentClass.b2 = this.lastClass;
        this.currentPlayer.b2 = this.player;
        this.countRounds += 1;

        this.winner();
        this.setNextPlayer();
        this.setNextClass();
        if (this.countRounds == 9 && !this.setWinner) {
          this.setWinner = "Empate";
        }
      } else if (id === "c2") {
        this.currentClass.c2 = this.lastClass;
        this.currentPlayer.c2 = this.player;
        this.countRounds += 1;

        this.winner();
        this.setNextPlayer();
        this.setNextClass();
        if (this.countRounds == 9 && !this.setWinner) {
          this.setWinner = "Empate";
        }
      } else if (id === "a3") {
        this.currentClass.a3 = this.lastClass;
        this.currentPlayer.a3 = this.player;
        this.countRounds += 1;

        this.winner();
        this.setNextPlayer();
        this.setNextClass();
        if (this.countRounds == 9 && !this.setWinner) {
          this.setWinner = "Empate";
        }
      } else if (id === "b3") {
        this.currentClass.b3 = this.lastClass;
        this.currentPlayer.b3 = this.player;
        this.countRounds += 1;

        this.winner();
        this.setNextPlayer();
        this.setNextClass();
        if (this.countRounds == 9 && !this.setWinner) {
          this.setWinner = "Empate";
        }
      } else if (id === "c3") {
        this.currentClass.c3 = this.lastClass;
        this.currentPlayer.c3 = this.player;
        this.countRounds += 1;

        this.winner();
        this.setNextPlayer();
        this.setNextClass();
        if (this.countRounds == 9 && !this.setWinner) {
          this.setWinner = "Empate";
        }
      }
    },
    setNextPlayer() {
      this.player === "Player 1"
        ? (this.player = "Player 2")
        : (this.player = "Player 1");
    },
    setNextClass() {
      this.lastClass === "red"
        ? (this.lastClass = "blue")
        : (this.lastClass = "red");
    },
    reset() {
      this.countRounds = 0;
      this.player = "Player 1";
      this.lastClass = "red";
      this.currentClass = {
        a1: "a1",
        b1: "b1",
        c1: "c1",
        a2: "a2",
        b2: "b2",
        c2: "c2",
        a3: "a3",
        b3: "b3",
        c3: "c3"
      };
      this.currentPlayer = {
        a1: "a1",
        b1: "b1",
        c1: "c1",
        a2: "a2",
        b2: "b2",
        c2: "c2",
        a3: "a3",
        b3: "b3",
        c3: "c3"
      };
      this.setWinner = "";
    },

    winner() {
      const win = "green";
      const lose = "gray";
      const a1 = this.currentClass.a1;
      const b1 = this.currentClass.b1;
      const c1 = this.currentClass.c1;
      const a2 = this.currentClass.a2;
      const b2 = this.currentClass.b2;
      const c2 = this.currentClass.c2;
      const a3 = this.currentClass.a3;
      const b3 = this.currentClass.b3;
      const c3 = this.currentClass.c3;

      console.log("a1- " + a1);
      console.log("a2- " + a2);
      console.log("a3- " + a3);
      console.log("b1- " + b1);
      console.log("b2- " + b2);
      console.log("b3- " + b3);
      console.log("c1- " + c1);
      console.log("c2- " + c2);
      console.log("c3- " + c3);
      if (a1 === "red" || a1 === "blue") {
        console.log("Condição com a1");
        if (a1 === a2 && a1 === a3) {
          //primeira condição de vitoria
          console.log("1º condição de vitoria");
          this.currentClass = {
            a1: win,
            b1: lose,
            c1: lose,
            a2: win,
            b2: lose,
            c2: lose,
            a3: win,
            b3: lose,
            c3: lose
          };
          this.setWinner = `O ganhador é o ${this.currentPlayer.a1}`;
        } else if (a1 === b2 && a1 === c3) {
          //segunda condição de vitoria

          console.log("2º condição de vitoria");
          this.currentClass = {
            a1: win,
            b1: lose,
            c1: lose,
            a2: lose,
            b2: win,
            c2: lose,
            a3: lose,
            b3: lose,
            c3: win
          };
          this.setWinner = `O ganhador é o ${this.currentPlayer.a1}`;
        } else if (a1 === b1 && a1 === c1) {
          //terceira condição de vitoria
          console.log("3º condição de vitoria");
          this.currentClass = {
            a1: win,
            b1: win,
            c1: win,
            a2: lose,
            b2: lose,
            c2: lose,
            a3: lose,
            b3: lose,
            c3: lose
          };
          this.setWinner = `O ganhador é o ${this.currentPlayer.a1}`;
        }
      }
      if (a2 === "red" || a2 === "blue") {
        console.log("Condição com a2");
        if (a2 === b2 && a2 === c2) {
          //quarta condição de vitoria
          console.log("4º condição de vitoria");
          this.currentClass = {
            a1: lose,
            b1: lose,
            c1: lose,
            a2: win,
            b2: win,
            c2: win,
            a3: lose,
            b3: lose,
            c3: lose
          };
          this.setWinner = `O ganhador é o ${this.currentPlayer.a2}`;
        }
      }
      if (a3 === "red" || a3 === "blue") {
        console.log("condição com a3");
        if (a3 === b2 && a3 === c1) {
          //quinta condição de vitoria
          console.log("5º condição de vitoria");
          this.currentClass = {
            a1: lose,
            b1: lose,
            c1: win,
            a2: lose,
            b2: win,
            c2: lose,
            a3: win,
            b3: lose,
            c3: lose
          };
          this.setWinner = `O ganhador é o ${this.currentPlayer.a3}`;
        } else if (a3 === b3 && a3 === c3) {
          //sexta condição de vitoria
          console.log("6º condição de vitoria");
          this.currentClass = {
            a1: lose,
            b1: lose,
            c1: lose,
            a2: lose,
            b2: lose,
            c2: lose,
            a3: win,
            b3: win,
            c3: win
          };
          this.setWinner = `O ganhador é o ${this.currentPlayer.a3}`;
        }
      }
      if (b1 === "red" || b1 === "blue") {
        console.log("condição com b1");
        if (b1 === b2 && b1 === b3) {
          //setima condição de vitoria
          console.log("7º condição de vitoria");
          this.currentClass = {
            a1: lose,
            b1: win,
            c1: lose,
            a2: lose,
            b2: win,
            c2: lose,
            a3: lose,
            b3: win,
            c3: lose
          };
          this.setWinner = `O ganhador é o ${this.currentPlayer.b1}`;
        }
      }
      if (c1 === "red" || c1 === "blue") {
        console.log("condição com c1");
        if (c1 === c3 && c1 === c2) {
          //oitava condição de vitoria
          console.log("8º condição de vitoria");
          this.currentClass = {
            a1: lose,
            b1: lose,
            c1: win,
            a2: lose,
            b2: lose,
            c2: win,
            a3: lose,
            b3: lose,
            c3: win
          };
          this.setWinner = this.currentClass.c1;
        }
      }
    }
  }
};
</script>

<style>
.tableConteiner {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  margin-top: 10rem;
}
.table {
  padding-top: 2rem;
  height: 24rem;
  width: 24rem;

  display: grid;
  grid-template-rows: 8rem 8rem 8rem;

  grid-template-areas: "row-a row-b row-c";
}

img {
  width: 4rem;
  height: auto;
}

button {
  font-size: 1rem;
  text-transform: uppercase;
  font-weight: bold;

  padding: 10px;
  border-radius: 10px;
  margin: 3rem;
  outline: none;
  cursor: pointer;
}

h2 {
  font-size: auto;
  border-bottom: 2px solid #000;
  text-transform: uppercase;
  margin: 3rem 0;
}

.reset-button {
  background: #ff9100;
  color: #333;
}
.new-game-button {
  background: #0ca70c;
  color: #333;
}

.gray,
.green,
.blue,
.red {
  color: #ddd !important;
  cursor: pointer;

  display: flex;
  align-items: center;
  justify-content: center;

  width: 8rem;
  height: 100%;
}

.red {
  background: #cc1919a0 !important;
}
.blue {
  background: #1981d6a0 !important;
}
.green {
  background: #168f16a0 !important;
}
.gray {
  color: transparent !important;
  background: #444444a0 !important;
}

.red:hover {
  background: #ff6666a0 !important;
}
.blue:hover {
  background: #66c2ffa0 !important;
}
.green:hover {
  background: #66ff66a0 !important;
}
.gray:hover {
  color: transparent !important;
  background: #666666a0 !important;
}

.a1:hover,
.a2:hover,
.a3:hover,
.b1:hover,
.b2:hover,
.b3:hover,
.c1:hover,
.c2:hover,
.c3:hover {
  background: #05050511;
}

.a1 {
  border-right: var(--border);
  border-bottom: var(--border);
}
.a2 {
  border-right: var(--border);
  border-bottom: var(--border);
  border-left: var(--border);
}
.a3 {
  border-bottom: var(--border);
  border-left: var(--border);
}
.b1 {
  border-top: var(--border);
  border-right: var(--border);
  border-bottom: var(--border);
}
.b2 {
  border-top: var(--border);
  border-right: var(--border);
  border-bottom: var(--border);
  border-left: var(--border);
}
.b3 {
  border-top: var(--border);
  border-bottom: var(--border);
  border-left: var(--border);
}
.c1 {
  border-top: var(--border);
  border-right: var(--border);
}
.c2 {
  border-top: var(--border);
  border-right: var(--border);
  border-left: var(--border);
}
.c3 {
  border-top: var(--border);
  border-left: var(--border);
}

.a1,
.a2,
.a3,
.b1,
.b2,
.b3,
.c1,
.c2,
.c3 {
  color: #666;
  cursor: pointer;
  background: #fafafa;

  display: flex;
  align-items: center;
  justify-content: center;

  width: 8rem;
  height: 100%;
}
</style>
