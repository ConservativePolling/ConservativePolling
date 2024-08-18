import React, { useState } from 'react';

function SimpleElectionGame() {
  const [votes, setVotes] = useState({ candidate1: 0, candidate2: 0 });

  const handleVote = (candidate) => {
    setVotes(prev => ({
      ...prev,
      [candidate]: prev[candidate] + 1
    }));
  };

  return (
    <div style={{ fontFamily: 'Arial, sans-serif', padding: '20px', maxWidth: '400px', margin: '0 auto' }}>
      <h1 style={{ textAlign: 'center' }}>Simple Election Game</h1>
      <div style={{ display: 'flex', justifyContent: 'space-between', marginBottom: '20px' }}>
        <div>
          <h2>Candidate 1</h2>
          <p>Votes: {votes.candidate1}</p>
          <button onClick={() => handleVote('candidate1')} style={{ padding: '10px', backgroundColor: 'lightblue' }}>
            Vote for Candidate 1
          </button>
        </div>
        <div>
          <h2>Candidate 2</h2>
          <p>Votes: {votes.candidate2}</p>
          <button onClick={() => handleVote('candidate2')} style={{ padding: '10px', backgroundColor: 'lightgreen' }}>
            Vote for Candidate 2
          </button>
        </div>
      </div>
      <p style={{ textAlign: 'center' }}>Total Votes: {votes.candidate1 + votes.candidate2}</p>
    </div>
  );
}

export default SimpleElectionGame;
