
// AdminDashboard.jsx
import React, { useState } from 'react';

export default function AdminDashboard() {
  const [round, setRound] = useState('');
  const [color, setColor] = useState('');

  const setResult = async () => {
    await fetch('http://YOUR_SERVER/admin/setresult', {
      method: 'POST',
      headers: { 'Content-Type': 'application/json' },
      body: JSON.stringify({ round, color }),
    });
    alert('Result Updated!');
  };

  return (
    <div>
      <h2>Admin Panel</h2>
      <input placeholder="Round No." value={round} onChange={e => setRound(e.target.value)} />
      <input placeholder="Winning Color" value={color} onChange={e => setColor(e.target.value)} />
      <button onClick={setResult}>Set Result</button>
    </div>
  );
}
