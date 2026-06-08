
<style>
  :root {
    --brand-dark: #00353e;
    --brand-gold: #bd9d4c;
    --brand-slate: #405a5a;
    --brand-forest: #3e4f37;
    --brand-sage: #858b65;
    --brand-cream: #e0dcd2;
    --brand-white: #ffffff;
  }
  * { box-sizing: border-box; margin: 0; padding: 0; }
  body { font-family: var(--font-sans, sans-serif); }

  .header {
    background: var(--brand-dark);
    color: var(--brand-white);
    padding: 20px 24px 16px;
    border-radius: var(--border-radius-lg, 12px);
    margin-bottom: 20px;
  }
  .header-top { display: flex; align-items: center; gap: 12px; margin-bottom: 8px; }
  .header h1 { font-size: 20px; font-weight: 500; color: var(--brand-white); }
  .header-sub { font-size: 13px; color: var(--brand-cream); opacity: 0.85; }
  .gold-bar { width: 36px; height: 3px; background: var(--brand-gold); border-radius: 2px; margin-top: 10px; }

  .tabs {
    display: flex; gap: 6px; margin-bottom: 20px; flex-wrap: wrap;
  }
  .tab {
    padding: 7px 16px; border-radius: 20px; font-size: 13px; cursor: pointer;
    border: 1.5px solid transparent; font-weight: 500; transition: all 0.15s;
    background: var(--color-background-secondary);
    color: var(--color-text-secondary);
    border-color: var(--color-border-tertiary);
  }
  .tab.active { background: var(--brand-dark); color: var(--brand-white); border-color: var(--brand-dark); }
  .tab:hover:not(.active) { border-color: var(--brand-slate); color: var(--color-text-primary); }

  .section { display: none; }
  .section.active { display: block; }

  .day-header {
    display: flex; align-items: center; gap: 10px;
    margin-bottom: 16px;
  }
  .day-badge {
    background: var(--brand-gold); color: var(--brand-dark);
    font-size: 11px; font-weight: 500; padding: 3px 10px;
    border-radius: 20px; letter-spacing: 0.5px;
  }
  .day-title { font-size: 15px; font-weight: 500; color: var(--color-text-primary); }

  .driver-grid { display: grid; grid-template-columns: repeat(auto-fit, minmax(300px, 1fr)); gap: 14px; margin-bottom: 24px; }

  .driver-card {
    border: 0.5px solid var(--color-border-tertiary);
    border-radius: var(--border-radius-lg, 12px);
    overflow: hidden;
    background: var(--color-background-primary);
  }
  .driver-card-head {
    padding: 12px 16px;
    display: flex; align-items: center; gap: 10px;
    border-bottom: 0.5px solid var(--color-border-tertiary);
  }
  .driver-avatar {
    width: 36px; height: 36px; border-radius: 50%;
    display: flex; align-items: center; justify-content: center;
    font-size: 13px; font-weight: 500;
    flex-shrink: 0;
  }
  .av-rental { background: #e0f0ee; color: var(--brand-dark); }
  .av-own { background: #f3eed8; color: #7a5c10; }
  .driver-name { font-size: 15px; font-weight: 500; color: var(--color-text-primary); }
  .driver-type { font-size: 11px; color: var(--color-text-secondary); margin-top: 1px; }

  .task-list { padding: 10px 16px 14px; }
  .task-item {
    display: flex; gap: 10px; padding: 8px 0;
    border-bottom: 0.5px solid var(--color-border-tertiary);
  }
  .task-item:last-child { border-bottom: none; }
  .task-time {
    font-size: 11px; font-weight: 500; color: var(--brand-slate);
    min-width: 44px; padding-top: 2px; flex-shrink: 0;
  }
  .task-text { font-size: 13px; color: var(--color-text-primary); line-height: 1.55; }
  .task-icon { font-size: 14px; color: var(--brand-sage); padding-top: 2px; flex-shrink: 0; }
  .pax-tag {
    display: inline-block; background: var(--color-background-secondary);
    color: var(--color-text-secondary); font-size: 11px;
    padding: 1px 7px; border-radius: 10px; margin: 2px 2px 0 0;
  }
  .route-tag {
    display: inline-flex; align-items: center; gap: 4px;
    font-size: 11px; color: var(--brand-gold); font-weight: 500; margin-top: 3px;
  }
  .parking-note {
    background: #fdf8ed; border: 0.5px solid #e8d5a0;
    border-radius: 6px; padding: 6px 10px; margin-top: 6px;
    font-size: 11px; color: #7a5c10; display: flex; gap: 6px; align-items: flex-start;
  }

  .master-table { width: 100%; border-collapse: collapse; font-size: 13px; }
  .master-table th {
    background: var(--brand-dark); color: var(--brand-white);
    padding: 9px 12px; text-align: left; font-weight: 500; font-size: 12px;
  }
  .master-table th:first-child { border-radius: 8px 0 0 0; }
  .master-table th:last-child { border-radius: 0 8px 0 0; }
  .master-table td { padding: 9px 12px; border-bottom: 0.5px solid var(--color-border-tertiary); vertical-align: top; }
  .master-table tr:last-child td { border-bottom: none; }
  .master-table tr:nth-child(even) td { background: var(--color-background-secondary); }
  .master-table-wrap { border: 0.5px solid var(--color-border-tertiary); border-radius: 10px; overflow: hidden; margin-bottom: 24px; }
  .day1-row { border-left: 3px solid var(--brand-gold); }
  .day2-row { border-left: 3px solid var(--brand-forest); }

  .map-section { margin-bottom: 24px; }
  .map-title { font-size: 14px; font-weight: 500; margin-bottom: 12px; color: var(--color-text-primary); }
  .location-grid { display: grid; grid-template-columns: repeat(auto-fit, minmax(220px, 1fr)); gap: 10px; }
  .location-card {
    border: 0.5px solid var(--color-border-tertiary);
    border-radius: var(--border-radius-md, 8px);
    padding: 12px; background: var(--color-background-primary);
    cursor: pointer; transition: border-color 0.15s;
    text-decoration: none; display: block;
  }
  .location-card:hover { border-color: var(--brand-gold); }
  .loc-name { font-size: 13px; font-weight: 500; color: var(--color-text-primary); margin-bottom: 3px; }
  .loc-addr { font-size: 11px; color: var(--color-text-secondary); line-height: 1.5; }
  .loc-map-btn {
    display: inline-flex; align-items: center; gap: 4px;
    margin-top: 8px; font-size: 11px; color: var(--brand-slate);
    border: 0.5px solid var(--color-border-secondary);
    padding: 3px 9px; border-radius: 10px;
    cursor: pointer; background: none; font-family: inherit;
    transition: all 0.12s;
  }
  .loc-map-btn:hover { background: var(--brand-dark); color: var(--brand-white); border-color: var(--brand-dark); }

  .map-embed {
    width: 100%; height: 360px; border-radius: var(--border-radius-lg, 12px);
    border: 0.5px solid var(--color-border-tertiary); margin-bottom: 10px;
    overflow: hidden;
  }
  .map-embed iframe { width: 100%; height: 100%; border: none; }

  .legend { display: flex; gap: 16px; flex-wrap: wrap; margin-bottom: 20px; }
  .legend-item { display: flex; align-items: center; gap: 6px; font-size: 12px; color: var(--color-text-secondary); }
  .legend-dot { width: 10px; height: 10px; border-radius: 50%; flex-shrink: 0; }

  .driver-filter { display: flex; gap: 6px; flex-wrap: wrap; margin-bottom: 16px; }
  .filter-btn {
    padding: 5px 13px; border-radius: 16px; font-size: 12px; cursor: pointer;
    border: 1px solid var(--color-border-secondary);
    background: var(--color-background-primary);
    color: var(--color-text-secondary); font-family: inherit;
    transition: all 0.12s;
  }
  .filter-btn.on { background: var(--brand-slate); color: white; border-color: var(--brand-slate); }

  .driver-personal-card {
    border: 0.5px solid var(--color-border-tertiary);
    border-radius: var(--border-radius-lg, 12px);
    overflow: hidden; margin-bottom: 20px;
    background: var(--color-background-primary);
  }
  .dpc-head {
    background: var(--brand-dark); color: var(--brand-white);
    padding: 14px 18px; display: flex; align-items: center; gap: 12px;
  }
  .dpc-avatar {
    width: 42px; height: 42px; border-radius: 50%;
    background: var(--brand-gold); color: var(--brand-dark);
    display: flex; align-items: center; justify-content: center;
    font-size: 15px; font-weight: 500; flex-shrink: 0;
  }
  .dpc-name { font-size: 17px; font-weight: 500; }
  .dpc-sub { font-size: 12px; color: var(--brand-cream); opacity: 0.8; margin-top: 2px; }
  .dpc-body { padding: 14px 18px; }
  .dpc-day-label {
    font-size: 11px; font-weight: 500; letter-spacing: 0.5px;
    color: var(--brand-slate); text-transform: uppercase;
    margin: 12px 0 8px;
    display: flex; align-items: center; gap: 8px;
  }
  .dpc-day-label::after { content: ''; flex: 1; height: 0.5px; background: var(--color-border-tertiary); }
  .dpc-task {
    display: flex; gap: 10px; padding: 9px 0;
    border-bottom: 0.5px solid var(--color-border-tertiary);
  }
  .dpc-task:last-child { border-bottom: none; }
  .dpc-seq {
    width: 22px; height: 22px; border-radius: 50%;
    background: var(--brand-cream); color: var(--brand-dark);
    font-size: 11px; font-weight: 500;
    display: flex; align-items: center; justify-content: center;
    flex-shrink: 0; margin-top: 1px;
  }
  .dpc-task-content { font-size: 13px; color: var(--color-text-primary); line-height: 1.55; }
</style>

<h2 class="sr-only">Auckland transport car plan for Day 1 and Day 2, with master list and individual driver schedules</h2>

<div class="header">
  <div class="header-top">
    <i class="ti ti-car" aria-hidden="true" style="font-size:22px; color: var(--brand-gold);"></i>
    <h1>Auckland Transport Plan</h1>
  </div>
  <div class="header-sub">5 drivers &nbsp;·&nbsp; 2 days &nbsp;·&nbsp; Coordinated vehicle logistics</div>
  <div class="gold-bar"></div>
</div>

<div class="tabs">
  <button class="tab active" onclick="showTab('master')"><i class="ti ti-list" aria-hidden="true"></i> Master list</button>
  <button class="tab" onclick="showTab('day1')"><i class="ti ti-calendar-event" aria-hidden="true"></i> Day 1</button>
  <button class="tab" onclick="showTab('day2')"><i class="ti ti-calendar-event" aria-hidden="true"></i> Day 2</button>
  <button class="tab" onclick="showTab('drivers')"><i class="ti ti-user" aria-hidden="true"></i> By driver</button>
  <button class="tab" onclick="showTab('locations')"><i class="ti ti-map-pin" aria-hidden="true"></i> Locations</button>
</div>

<div id="tab-master" class="section active">
  <div class="day-header">
    <span class="day-badge">MASTER</span>
    <span class="day-title">All tasks across both days</span>
  </div>
  <div class="legend">
    <div class="legend-item"><div class="legend-dot" style="background:#bd9d4c"></div> Day 1</div>
    <div class="legend-item"><div class="legend-dot" style="background:#3e4f37"></div> Day 2</div>
    <div class="legend-item"><div class="legend-dot" style="background:#00353e"></div> Rental vehicle</div>
    <div class="legend-item"><div class="legend-dot" style="background:#858b65"></div> Own vehicle</div>
  </div>
  <div class="master-table-wrap">
    <table class="master-table">
      <thead>
        <tr>
          <th>Day</th>
          <th>Driver</th>
          <th>Vehicle</th>
          <th>Time</th>
          <th>Task</th>
          <th>Passengers</th>
          <th>Route</th>
        </tr>
      </thead>
      <tbody>
        <tr class="day1-row"><td>Day 1</td><td>Reuben</td><td>Rental</td><td>6:30am</td><td>Pickup</td><td>Bryn, Jeanine</td><td>Radisson Red → IC</td></tr>
        <tr class="day1-row"><td>Day 1</td><td>Reuben</td><td>Rental</td><td>-</td><td>Drop-off</td><td>2 team members</td><td>→ JW Marriott</td></tr>
        <tr class="day1-row"><td>Day 1</td><td>Reuben</td><td>Rental</td><td>-</td><td>Drop-off</td><td>Shannelle, Sarah, Ryan</td><td>→ Radisson Red</td></tr>
        <tr class="day1-row"><td>Day 1</td><td>Geoff</td><td>Rental</td><td>-</td><td>Collect rental + pickup</td><td>4 people</td><td>Airport → IC</td></tr>
        <tr class="day1-row"><td>Day 1</td><td>Geoff</td><td>Rental</td><td>-</td><td>Drop-off</td><td>2 team members</td><td>→ JW Marriott</td></tr>
        <tr class="day1-row"><td>Day 1</td><td>Geoff</td><td>Rental</td><td>-</td><td>Drop-off</td><td>Darwin</td><td>→ DC</td></tr>
        <tr class="day1-row"><td>Day 1</td><td>Ben</td><td>Own</td><td>-</td><td>Pickup</td><td>4 people</td><td>Airport → IC</td></tr>
        <tr class="day1-row"><td>Day 1</td><td>Ben</td><td>Own</td><td>-</td><td>Hotel visit</td><td>Team</td><td>→ Hotel Britomart</td></tr>
        <tr class="day1-row"><td>Day 1</td><td>Ben</td><td>Own</td><td>-</td><td>Drop-off</td><td>Bryn</td><td>→ Radisson Red</td></tr>
        <tr class="day1-row"><td>Day 1</td><td>Ben</td><td>Own</td><td>-</td><td>Return</td><td>Rest of team</td><td>→ DC</td></tr>
        <tr class="day1-row"><td>Day 1</td><td>Greg</td><td>Own</td><td>-</td><td>Hotel visit</td><td>Team</td><td>→ Hotel Britomart</td></tr>
        <tr class="day1-row"><td>Day 1</td><td>Greg</td><td>Own</td><td>-</td><td>Drop-off</td><td>Anton, Jack, Rilla</td><td>→ Hotel</td></tr>
        <tr class="day1-row"><td>Day 1</td><td>Greg</td><td>Own</td><td>-</td><td>Drop-off</td><td>Andrew</td><td>→ DC</td></tr>
        <tr class="day1-row"><td>Day 1</td><td>Brent</td><td>Own</td><td>-</td><td>Hotel visit</td><td>Team</td><td>→ Pullman Auckland Airport</td></tr>
        <tr class="day1-row"><td>Day 1</td><td>Brent</td><td>Own</td><td>-</td><td>Drop-off</td><td>Marcus, Hardeep, Mata</td><td>→ DC</td></tr>
        <tr class="day1-row"><td>Day 1</td><td>Brent</td><td>Own</td><td>-</td><td>Drop-off</td><td>Jeanine</td><td>→ Radisson Red</td></tr>
        <tr class="day2-row"><td>Day 2</td><td>Reuben</td><td>Rental</td><td>6:40am</td><td>Pickup</td><td>Mike Clark, Bryn, Rilla</td><td>→ Park Hyatt</td></tr>
        <tr class="day2-row"><td>Day 2</td><td>Reuben</td><td>Rental</td><td>4:45pm</td><td>Drop-off</td><td>Sarah, Jack, Bryn, Rilla</td><td>→ Airport</td></tr>
        <tr class="day2-row"><td>Day 2</td><td>Geoff</td><td>Rental</td><td>7:30am</td><td>Pickup</td><td>Marcus + 3 team</td><td>DC → Park Hyatt</td></tr>
        <tr class="day2-row"><td>Day 2</td><td>Geoff</td><td>Rental</td><td>-</td><td>Return</td><td>Marcus + same team</td><td>→ DC</td></tr>
        <tr class="day2-row"><td>Day 2</td><td>Brent</td><td>Own</td><td>7:45am</td><td>Pickup</td><td>Sarah, Jack, Jeanine</td><td>Radisson Red → Park Hyatt</td></tr>
        <tr class="day2-row"><td>Day 2</td><td>Brent</td><td>Own</td><td>-</td><td>Drop-off</td><td>Jeanine, Mike</td><td>→ Radisson Red</td></tr>
        <tr class="day2-row"><td>Day 2</td><td>Ben</td><td>Own</td><td>7:45am</td><td>Pickup</td><td>Shannelle, Anton, Ryan</td><td>Radisson Red → Park Hyatt</td></tr>
        <tr class="day2-row"><td>Day 2</td><td>Ben</td><td>Own</td><td>-</td><td>Return</td><td>Same team</td><td>→ Airport</td></tr>
        <tr class="day2-row"><td>Day 2</td><td>Greg</td><td>Own</td><td>7:30am</td><td>Pickup</td><td>Richard, Braden + 2 team</td><td>DC → Park Hyatt</td></tr>
        <tr class="day2-row"><td>Day 2</td><td>Greg</td><td>Own</td><td>-</td><td>Return</td><td>Same team</td><td>→ DC</td></tr>
      </tbody>
    </table>
  </div>
</div>

<div id="tab-day1" class="section">
  <div class="day-header">
    <span class="day-badge">DAY 1</span>
    <span class="day-title">Airport pickups, IC arrivals & hotel visits</span>
  </div>
  <div class="driver-grid">

    <div class="driver-card">
      <div class="driver-card-head">
        <div class="driver-avatar av-rental">RE</div>
        <div>
          <div class="driver-name">Reuben</div>
          <div class="driver-type">Rental vehicle</div>
        </div>
      </div>
      <div class="task-list">
        <div class="task-item">
          <div class="task-time">6:30am</div>
          <i class="ti ti-map-pin task-icon" aria-hidden="true"></i>
          <div class="task-text">Pick up <span class="pax-tag">Bryn</span><span class="pax-tag">Jeanine</span> from Radisson Red → IC</div>
        </div>
        <div class="task-item">
          <div class="task-time">-</div>
          <i class="ti ti-building task-icon" aria-hidden="true"></i>
          <div class="task-text">Take <span class="pax-tag">2 team members</span> to JW Marriott</div>
        </div>
        <div class="task-item">
          <div class="task-time">-</div>
          <i class="ti ti-home task-icon" aria-hidden="true"></i>
          <div class="task-text">Drop <span class="pax-tag">Shannelle</span><span class="pax-tag">Sarah</span><span class="pax-tag">Ryan</span> to Radisson Red Hotel</div>
        </div>
      </div>
    </div>

    <div class="driver-card">
      <div class="driver-card-head">
        <div class="driver-avatar av-rental">GE</div>
        <div>
          <div class="driver-name">Geoff</div>
          <div class="driver-type">Rental vehicle</div>
        </div>
      </div>
      <div class="task-list">
        <div class="task-item">
          <div class="task-time">-</div>
          <i class="ti ti-key task-icon" aria-hidden="true"></i>
          <div class="task-text">Collect rental, pick up <span class="pax-tag">4 people</span> from Airport → IC</div>
        </div>
        <div class="task-item">
          <div class="task-time">-</div>
          <i class="ti ti-building task-icon" aria-hidden="true"></i>
          <div class="task-text">Take <span class="pax-tag">2 team members</span> to JW Marriott</div>
        </div>
        <div class="task-item">
          <div class="task-time">-</div>
          <i class="ti ti-arrow-right task-icon" aria-hidden="true"></i>
          <div class="task-text">Drop <span class="pax-tag">Darwin</span> back to DC</div>
        </div>
      </div>
    </div>

    <div class="driver-card">
      <div class="driver-card-head">
        <div class="driver-avatar av-own">BE</div>
        <div>
          <div class="driver-name">Ben</div>
          <div class="driver-type">Own vehicle</div>
        </div>
      </div>
      <div class="task-list">
        <div class="task-item">
          <div class="task-time">-</div>
          <i class="ti ti-plane-arrival task-icon" aria-hidden="true"></i>
          <div class="task-text">Collect <span class="pax-tag">4 people</span> from Airport → IC</div>
        </div>
        <div class="task-item">
          <div class="task-time">-</div>
          <i class="ti ti-building task-icon" aria-hidden="true"></i>
          <div class="task-text">Take <span class="pax-tag">Team</span> to Hotel Britomart</div>
        </div>
        <div class="task-item">
          <div class="task-time">-</div>
          <i class="ti ti-home task-icon" aria-hidden="true"></i>
          <div class="task-text">Drop <span class="pax-tag">Bryn</span> to Radisson Red after hotel visit</div>
        </div>
        <div class="task-item">
          <div class="task-time">-</div>
          <i class="ti ti-arrow-back task-icon" aria-hidden="true"></i>
          <div class="task-text">Return <span class="pax-tag">rest of team</span> to DC</div>
        </div>
      </div>
    </div>

    <div class="driver-card">
      <div class="driver-card-head">
        <div class="driver-avatar av-own">GR</div>
        <div>
          <div class="driver-name">Greg</div>
          <div class="driver-type">Own vehicle</div>
        </div>
      </div>
      <div class="task-list">
        <div class="task-item">
          <div class="task-time">-</div>
          <i class="ti ti-building task-icon" aria-hidden="true"></i>
          <div class="task-text">Take <span class="pax-tag">Team</span> to Hotel Britomart</div>
        </div>
        <div class="task-item">
          <div class="task-time">-</div>
          <i class="ti ti-home task-icon" aria-hidden="true"></i>
          <div class="task-text">Drop <span class="pax-tag">Anton</span><span class="pax-tag">Jack</span><span class="pax-tag">Rilla</span> to hotel</div>
        </div>
        <div class="task-item">
          <div class="task-time">-</div>
          <i class="ti ti-arrow-back task-icon" aria-hidden="true"></i>
          <div class="task-text">Take <span class="pax-tag">Andrew</span> back to DC</div>
        </div>
      </div>
    </div>

    <div class="driver-card">
      <div class="driver-card-head">
        <div class="driver-avatar av-own">BR</div>
        <div>
          <div class="driver-name">Brent</div>
          <div class="driver-type">Own vehicle</div>
        </div>
      </div>
      <div class="task-list">
        <div class="task-item">
          <div class="task-time">-</div>
          <i class="ti ti-building task-icon" aria-hidden="true"></i>
          <div class="task-text">Take <span class="pax-tag">Team</span> to Pullman Auckland Airport</div>
        </div>
        <div class="task-item">
          <div class="task-time">-</div>
          <i class="ti ti-arrow-back task-icon" aria-hidden="true"></i>
          <div class="task-text">Drop <span class="pax-tag">Marcus</span><span class="pax-tag">Hardeep</span><span class="pax-tag">Mata</span> to DC</div>
        </div>
        <div class="task-item">
          <div class="task-time">-</div>
          <i class="ti ti-home task-icon" aria-hidden="true"></i>
          <div class="task-text">Drop <span class="pax-tag">Jeanine</span> to Radisson Red</div>
        </div>
      </div>
    </div>

  </div>
</div>

<div id="tab-day2" class="section">
  <div class="day-header">
    <span class="day-badge" style="background: var(--brand-forest);">DAY 2</span>
    <span class="day-title">Park Hyatt visits & afternoon airport departures</span>
  </div>
  <div style="background: #fdf8ed; border: 0.5px solid #e8d5a0; border-radius: 8px; padding: 10px 14px; margin-bottom: 16px; font-size: 12px; color: #7a5c10; display: flex; gap: 8px; align-items: flex-start;">
    <i class="ti ti-parking" aria-hidden="true" style="font-size:15px; flex-shrink:0; margin-top:1px;"></i>
    <div><strong>Parking note for all Day 2 drivers visiting Park Hyatt:</strong> Park at Jellicoe Street Car Park, 37–55 Madden Street, Auckland CBD, Auckland 1010. Approx. 5 min walk to Park Hyatt. Note: pay attention to time limits — some user reports of fines.</div>
  </div>
  <div class="driver-grid">

    <div class="driver-card">
      <div class="driver-card-head">
        <div class="driver-avatar av-rental">RE</div>
        <div>
          <div class="driver-name">Reuben</div>
          <div class="driver-type">Rental vehicle</div>
        </div>
      </div>
      <div class="task-list">
        <div class="task-item">
          <div class="task-time">6:40am</div>
          <i class="ti ti-map-pin task-icon" aria-hidden="true"></i>
          <div class="task-text">Pick up <span class="pax-tag">Mike Clark</span><span class="pax-tag">Bryn</span><span class="pax-tag">Rilla</span> → Park Hyatt
            <div class="route-tag"><i class="ti ti-parking" aria-hidden="true"></i> Park at Jellicoe St Car Park</div>
          </div>
        </div>
        <div class="task-item">
          <div class="task-time">4:45pm</div>
          <i class="ti ti-plane-departure task-icon" aria-hidden="true"></i>
          <div class="task-text">Take <span class="pax-tag">Sarah</span><span class="pax-tag">Jack</span><span class="pax-tag">Bryn</span><span class="pax-tag">Rilla</span> to Airport</div>
        </div>
      </div>
    </div>

    <div class="driver-card">
      <div class="driver-card-head">
        <div class="driver-avatar av-rental">GE</div>
        <div>
          <div class="driver-name">Geoff</div>
          <div class="driver-type">Rental vehicle</div>
        </div>
      </div>
      <div class="task-list">
        <div class="task-item">
          <div class="task-time">7:30am</div>
          <i class="ti ti-map-pin task-icon" aria-hidden="true"></i>
          <div class="task-text">Pick up <span class="pax-tag">Marcus</span> + <span class="pax-tag">3 team</span> from DC → Park Hyatt
            <div class="route-tag"><i class="ti ti-parking" aria-hidden="true"></i> Park at Jellicoe St Car Park</div>
          </div>
        </div>
        <div class="task-item">
          <div class="task-time">-</div>
          <i class="ti ti-arrow-back task-icon" aria-hidden="true"></i>
          <div class="task-text">Return <span class="pax-tag">Marcus</span> + same team to DC</div>
        </div>
      </div>
    </div>

    <div class="driver-card">
      <div class="driver-card-head">
        <div class="driver-avatar av-own">BR</div>
        <div>
          <div class="driver-name">Brent</div>
          <div class="driver-type">Own vehicle</div>
        </div>
      </div>
      <div class="task-list">
        <div class="task-item">
          <div class="task-time">7:45am</div>
          <i class="ti ti-map-pin task-icon" aria-hidden="true"></i>
          <div class="task-text">Collect <span class="pax-tag">Sarah</span><span class="pax-tag">Jack</span><span class="pax-tag">Jeanine</span> from Radisson Red → Park Hyatt
            <div class="route-tag"><i class="ti ti-parking" aria-hidden="true"></i> Park at Jellicoe St Car Park</div>
          </div>
        </div>
        <div class="task-item">
          <div class="task-time">-</div>
          <i class="ti ti-home task-icon" aria-hidden="true"></i>
          <div class="task-text">Drop <span class="pax-tag">Jeanine</span><span class="pax-tag">Mike</span> to Radisson Red</div>
        </div>
      </div>
    </div>

    <div class="driver-card">
      <div class="driver-card-head">
        <div class="driver-avatar av-own">BE</div>
        <div>
          <div class="driver-name">Ben</div>
          <div class="driver-type">Own vehicle</div>
        </div>
      </div>
      <div class="task-list">
        <div class="task-item">
          <div class="task-time">7:45am</div>
          <i class="ti ti-map-pin task-icon" aria-hidden="true"></i>
          <div class="task-text">Collect <span class="pax-tag">Shannelle</span><span class="pax-tag">Anton</span><span class="pax-tag">Ryan</span> from Radisson Red → Park Hyatt
            <div class="route-tag"><i class="ti ti-parking" aria-hidden="true"></i> Park at Jellicoe St Car Park</div>
          </div>
        </div>
        <div class="task-item">
          <div class="task-time">-</div>
          <i class="ti ti-plane-departure task-icon" aria-hidden="true"></i>
          <div class="task-text">Return same team to Airport</div>
        </div>
      </div>
    </div>

    <div class="driver-card">
      <div class="driver-card-head">
        <div class="driver-avatar av-own">GR</div>
        <div>
          <div class="driver-name">Greg</div>
          <div class="driver-type">Own vehicle</div>
        </div>
      </div>
      <div class="task-list">
        <div class="task-item">
          <div class="task-time">7:30am</div>
          <i class="ti ti-map-pin task-icon" aria-hidden="true"></i>
          <div class="task-text">Pick up <span class="pax-tag">Richard</span><span class="pax-tag">Braden</span> + <span class="pax-tag">2 team</span> from DC → Park Hyatt
            <div class="route-tag"><i class="ti ti-parking" aria-hidden="true"></i> Park at Jellicoe St Car Park</div>
          </div>
        </div>
        <div class="task-item">
          <div class="task-time">-</div>
          <i class="ti ti-arrow-back task-icon" aria-hidden="true"></i>
          <div class="task-text">Return same team to DC</div>
        </div>
      </div>
    </div>

  </div>
</div>

<div id="tab-drivers" class="section">
  <div class="day-header">
    <span class="day-badge" style="background: var(--brand-slate);">DRIVERS</span>
    <span class="day-title">Individual schedule per driver</span>
  </div>

  <div class="driver-filter">
    <button class="filter-btn on" onclick="filterDriver('all', this)">All drivers</button>
    <button class="filter-btn" onclick="filterDriver('Reuben', this)">Reuben</button>
    <button class="filter-btn" onclick="filterDriver('Geoff', this)">Geoff</button>
    <button class="filter-btn" onclick="filterDriver('Ben', this)">Ben</button>
    <button class="filter-btn" onclick="filterDriver('Greg', this)">Greg</button>
    <button class="filter-btn" onclick="filterDriver('Brent', this)">Brent</button>
  </div>

  <div class="driver-personal-card" data-driver="Reuben">
    <div class="dpc-head">
      <div class="dpc-avatar">RE</div>
      <div><div class="dpc-name">Reuben</div><div class="dpc-sub">Rental vehicle · 2 days</div></div>
    </div>
    <div class="dpc-body">
      <div class="dpc-day-label">Day 1</div>
      <div class="dpc-task"><div class="dpc-seq">1</div><div class="dpc-task-content"><strong>6:30am</strong> — Pick up Bryn & Jeanine from Radisson Red Hotel and take to IC.</div></div>
      <div class="dpc-task"><div class="dpc-seq">2</div><div class="dpc-task-content">Take 2 team members to JW Marriott.</div></div>
      <div class="dpc-task"><div class="dpc-seq">3</div><div class="dpc-task-content">Take Shannelle, Sarah and Ryan to Radisson Red Hotel.</div></div>
      <div class="dpc-day-label">Day 2</div>
      <div class="dpc-task"><div class="dpc-seq">1</div><div class="dpc-task-content"><strong>6:40am</strong> — Take Mike Clark, Bryn & Rilla to Park Hyatt. Park at Jellicoe Street Car Park, 37–55 Madden Street, Auckland CBD (5 min walk to Park Hyatt).</div></div>
      <div class="dpc-task"><div class="dpc-seq">2</div><div class="dpc-task-content"><strong>4:45pm</strong> — Take Sarah, Jack, Bryn and Rilla back to Airport.</div></div>
    </div>
  </div>

  <div class="driver-personal-card" data-driver="Geoff">
    <div class="dpc-head">
      <div class="dpc-avatar">GE</div>
      <div><div class="dpc-name">Geoff</div><div class="dpc-sub">Rental vehicle · 2 days</div></div>
    </div>
    <div class="dpc-body">
      <div class="dpc-day-label">Day 1</div>
      <div class="dpc-task"><div class="dpc-seq">1</div><div class="dpc-task-content">Collect rental vehicle, then pick up 4 people from Airport and take to IC.</div></div>
      <div class="dpc-task"><div class="dpc-seq">2</div><div class="dpc-task-content">Take 2 team members to JW Marriott.</div></div>
      <div class="dpc-task"><div class="dpc-seq">3</div><div class="dpc-task-content">Drop Darwin back to DC.</div></div>
      <div class="dpc-day-label">Day 2</div>
      <div class="dpc-task"><div class="dpc-seq">1</div><div class="dpc-task-content"><strong>7:30am</strong> — Pick up Marcus and collect 3 team members from DC, drive to Park Hyatt. Park at Jellicoe Street Car Park, 37–55 Madden Street, Auckland CBD (5 min walk to Park Hyatt).</div></div>
      <div class="dpc-task"><div class="dpc-seq">2</div><div class="dpc-task-content">Take Marcus and same team members back to DC.</div></div>
    </div>
  </div>

  <div class="driver-personal-card" data-driver="Ben">
    <div class="dpc-head">
      <div class="dpc-avatar">BE</div>
      <div><div class="dpc-name">Ben</div><div class="dpc-sub">Own vehicle · 2 days</div></div>
    </div>
    <div class="dpc-body">
      <div class="dpc-day-label">Day 1</div>
      <div class="dpc-task"><div class="dpc-seq">1</div><div class="dpc-task-content">Collect 4 people from Airport and take to IC.</div></div>
      <div class="dpc-task"><div class="dpc-seq">2</div><div class="dpc-task-content">Take team to Hotel Britomart.</div></div>
      <div class="dpc-task"><div class="dpc-seq">3</div><div class="dpc-task-content">Drop Bryn to Radisson Red Hotel after hotel visit.</div></div>
      <div class="dpc-task"><div class="dpc-seq">4</div><div class="dpc-task-content">Return rest of team to DC.</div></div>
      <div class="dpc-day-label">Day 2</div>
      <div class="dpc-task"><div class="dpc-seq">1</div><div class="dpc-task-content"><strong>7:45am</strong> — Collect Shannelle, Anton & Ryan from Radisson Red, take to Park Hyatt. Park at Jellicoe Street Car Park, 37–55 Madden Street, Auckland CBD (5 min walk to Park Hyatt).</div></div>
      <div class="dpc-task"><div class="dpc-seq">2</div><div class="dpc-task-content">Return same team members to Airport.</div></div>
    </div>
  </div>

  <div class="driver-personal-card" data-driver="Greg">
    <div class="dpc-head">
      <div class="dpc-avatar">GR</div>
      <div><div class="dpc-name">Greg</div><div class="dpc-sub">Own vehicle · 2 days</div></div>
    </div>
    <div class="dpc-body">
      <div class="dpc-day-label">Day 1</div>
      <div class="dpc-task"><div class="dpc-seq">1</div><div class="dpc-task-content">Take team to Hotel Britomart.</div></div>
      <div class="dpc-task"><div class="dpc-seq">2</div><div class="dpc-task-content">Drop Anton, Jack and Rilla to hotel.</div></div>
      <div class="dpc-task"><div class="dpc-seq">3</div><div class="dpc-task-content">Take Andrew back to DC.</div></div>
      <div class="dpc-day-label">Day 2</div>
      <div class="dpc-task"><div class="dpc-seq">1</div><div class="dpc-task-content"><strong>7:30am</strong> — Pick up Richard and Braden and collect 2 team members from DC, drive to Park Hyatt. Park at Jellicoe Street Car Park, 37–55 Madden Street, Auckland CBD (5 min walk to Park Hyatt).</div></div>
      <div class="dpc-task"><div class="dpc-seq">2</div><div class="dpc-task-content">Take same team members back to DC.</div></div>
    </div>
  </div>

  <div class="driver-personal-card" data-driver="Brent">
    <div class="dpc-head">
      <div class="dpc-avatar">BR</div>
      <div><div class="dpc-name">Brent</div><div class="dpc-sub">Own vehicle · 2 days</div></div>
    </div>
    <div class="dpc-body">
      <div class="dpc-day-label">Day 1</div>
      <div class="dpc-task"><div class="dpc-seq">1</div><div class="dpc-task-content">Take team to Pullman Auckland Airport.</div></div>
      <div class="dpc-task"><div class="dpc-seq">2</div><div class="dpc-task-content">Drop Marcus, Hardeep & Mata to DC.</div></div>
      <div class="dpc-task"><div class="dpc-seq">3</div><div class="dpc-task-content">Drop Jeanine to Radisson Red Auckland.</div></div>
      <div class="dpc-day-label">Day 2</div>
      <div class="dpc-task"><div class="dpc-seq">1</div><div class="dpc-task-content"><strong>7:45am</strong> — Collect Sarah, Jack & Jeanine from Radisson Red, take to Park Hyatt. Park at Jellicoe Street Car Park, 37–55 Madden Street, Auckland CBD (5 min walk to Park Hyatt).</div></div>
      <div class="dpc-task"><div class="dpc-seq">2</div><div class="dpc-task-content">Take Jeanine and Mike to Radisson Red Auckland.</div></div>
    </div>
  </div>
</div>

<div id="tab-locations" class="section">
  <div class="day-header">
    <span class="day-badge" style="background: var(--brand-sage);">MAP</span>
    <span class="day-title">Drop-off & pick-up locations</span>
  </div>
  <p style="font-size:13px; color: var(--color-text-secondary); margin-bottom: 16px;">Click any location to open in Google Maps. IC and DC are internal venues not shown on public maps.</p>

  <div class="location-grid">
    <div class="location-card" onclick="openMap('Radisson RED Auckland, 33 Lorne Street, Auckland')">
      <div style="display:flex; align-items:center; gap:8px; margin-bottom:4px;">
        <i class="ti ti-building" aria-hidden="true" style="font-size:16px; color: var(--brand-gold);"></i>
        <div class="loc-name">Radisson Red Auckland</div>
      </div>
      <div class="loc-addr">33 Lorne Street, Auckland CBD, Auckland 1010</div>
      <button class="loc-map-btn"><i class="ti ti-map-2" aria-hidden="true"></i> Open in Maps</button>
    </div>

    <div class="location-card" onclick="openMap('JW Marriott Auckland, 22 Albert Street, Auckland')">
      <div style="display:flex; align-items:center; gap:8px; margin-bottom:4px;">
        <i class="ti ti-building" aria-hidden="true" style="font-size:16px; color: var(--brand-gold);"></i>
        <div class="loc-name">JW Marriott Auckland</div>
      </div>
      <div class="loc-addr">22/26 Albert Street, Auckland CBD, Auckland 1010</div>
      <button class="loc-map-btn"><i class="ti ti-map-2" aria-hidden="true"></i> Open in Maps</button>
    </div>

    <div class="location-card" onclick="openMap('Hotel Britomart Auckland, 29 Galway Street, Auckland')">
      <div style="display:flex; align-items:center; gap:8px; margin-bottom:4px;">
        <i class="ti ti-building" aria-hidden="true" style="font-size:16px; color: var(--brand-gold);"></i>
        <div class="loc-name">Hotel Britomart</div>
      </div>
      <div class="loc-addr">29 Galway Street, Auckland CBD, Auckland 1010</div>
      <button class="loc-map-btn"><i class="ti ti-map-2" aria-hidden="true"></i> Open in Maps</button>
    </div>

    <div class="location-card" onclick="openMap('Pullman Auckland Airport, 37 Tom Pearce Drive, Auckland')">
      <div style="display:flex; align-items:center; gap:8px; margin-bottom:4px;">
        <i class="ti ti-building" aria-hidden="true" style="font-size:16px; color: var(--brand-gold);"></i>
        <div class="loc-name">Pullman Auckland Airport</div>
      </div>
      <div class="loc-addr">37 Tom Pearce Drive, Māngere, Auckland 2022</div>
      <button class="loc-map-btn"><i class="ti ti-map-2" aria-hidden="true"></i> Open in Maps</button>
    </div>

    <div class="location-card" onclick="openMap('Park Hyatt Auckland, 99 Halsey Street, Auckland')">
      <div style="display:flex; align-items:center; gap:8px; margin-bottom:4px;">
        <i class="ti ti-building" aria-hidden="true" style="font-size:16px; color: var(--brand-gold);"></i>
        <div class="loc-name">Park Hyatt Auckland</div>
      </div>
      <div class="loc-addr">99 Halsey Street, Auckland CBD, Auckland 1010</div>
      <button class="loc-map-btn"><i class="ti ti-map-2" aria-hidden="true"></i> Open in Maps</button>
    </div>

    <div class="location-card" onclick="openMap('Jellicoe Street Car Park, 37-55 Madden Street, Auckland')">
      <div style="display:flex; align-items:center; gap:8px; margin-bottom:4px;">
        <i class="ti ti-parking" aria-hidden="true" style="font-size:16px; color: #3e4f37;"></i>
        <div class="loc-name">Jellicoe St Car Park</div>
      </div>
      <div class="loc-addr">37–55 Madden Street, Auckland CBD, Auckland 1010 · 5 min walk to Park Hyatt</div>
      <button class="loc-map-btn"><i class="ti ti-map-2" aria-hidden="true"></i> Open in Maps</button>
    </div>

    <div class="location-card" onclick="openMap('Auckland Airport, Ray Emery Drive, Māngere, Auckland')">
      <div style="display:flex; align-items:center; gap:8px; margin-bottom:4px;">
        <i class="ti ti-plane" aria-hidden="true" style="font-size:16px; color: var(--brand-slate);"></i>
        <div class="loc-name">Auckland Airport</div>
      </div>
      <div class="loc-addr">Ray Emery Drive, Māngere, Auckland 2022</div>
      <button class="loc-map-btn"><i class="ti ti-map-2" aria-hidden="true"></i> Open in Maps</button>
    </div>

    <div class="location-card" style="border-style: dashed; cursor: default;">
      <div style="display:flex; align-items:center; gap:8px; margin-bottom:4px;">
        <i class="ti ti-lock" aria-hidden="true" style="font-size:16px; color: var(--color-text-secondary);"></i>
        <div class="loc-name" style="color: var(--color-text-secondary);">IC & DC</div>
      </div>
      <div class="loc-addr">Internal venues — addresses not shown on public maps.</div>
    </div>
  </div>

  <div style="margin-top: 20px;">
    <div class="map-title">Auckland locations overview</div>
    <div class="map-embed">
      <iframe
        src="https://www.google.com/maps/embed/v1/search?key=AIzaSyD-9tSrke72PouQMnMX-a7eZSW0jkFMBWY&q=Park+Hyatt+Auckland,Hotel+Britomart+Auckland,JW+Marriott+Auckland,Radisson+Red+Auckland,Pullman+Auckland+Airport&zoom=13"
        allowfullscreen loading="lazy" referrerpolicy="no-referrer-when-downgrade">
      </iframe>
    </div>
    <p style="font-size:11px; color: var(--color-text-secondary); margin-top:6px;">
      <i class="ti ti-info-circle" aria-hidden="true"></i> Click individual location cards above to open precise directions in Google Maps.
    </p>
  </div>
</div>

<script>
function showTab(name) {
  document.querySelectorAll('.section').forEach(s => s.classList.remove('active'));
  document.querySelectorAll('.tab').forEach(t => t.classList.remove('active'));
  document.getElementById('tab-' + name).classList.add('active');
  event.target.closest('.tab').classList.add('active');
}

function filterDriver(name, btn) {
  document.querySelectorAll('.filter-btn').forEach(b => b.classList.remove('on'));
  btn.classList.add('on');
  document.querySelectorAll('.driver-personal-card').forEach(card => {
    card.style.display = (name === 'all' || card.dataset.driver === name) ? 'block' : 'none';
  });
}

function openMap(query) {
  const url = 'https://www.google.com/maps/search/?api=1&query=' + encodeURIComponent(query);
  openLink(url);
}
</script>
