# University-career-Fair-Hacker

Ruby Program

def maxEvents(arrival, duration)
  no_of_events = arrival.length-1
  time_interval = []
  non_hosted_events = []
  time_interval = (0..no_of_events).map do |i|
    [arrival[i], arrival[i] + duration[i]]
  end.sort {|e1, e2| e1[1] <=> e2[1]}

  last_interval = time_interval[0][1]
  (1..time_interval.length-1).each do|ind|
    if time_interval[ind][0] < last_interval
      non_hosted_events << 1
    else
      last_interval = last_interval[ind][1]
    end
  end
  (no_of_events - (non_hosted_events.length-1))
end
